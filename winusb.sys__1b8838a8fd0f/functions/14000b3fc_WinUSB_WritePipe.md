# WinUSB_WritePipe

- ea: `0x14000b3fc`
- end: `0x14000b661`
- name: `WinUSB_WritePipe`
- size: `613`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400026d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x1400075d8`
- `0x14000b3fc`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUSB_WritePipe(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int64 v7; // rax
  __int64 *v8; // r8
  PWDF_DRIVER_GLOBALS v9; // rcx
  __int64 v10; // r15
  int v11; // eax
  int v12; // edx
  unsigned int v13; // ebx
  int v14; // r9d
  __int64 v15; // r8
  char v16; // di
  __int64 v17; // rdx
  __int64 v18; // rbx
  int v19; // edx
  int v20; // eax
  char v22; // [rsp+28h] [rbp-60h]
  unsigned __int8 *v23; // [rsp+98h] [rbp+10h] BYREF

  v23 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      20,
      (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids);
  v7 = WdfFunctions_01015;
  v8 = off_140015040;
  v9 = WdfDriverGlobals;
  *a4 = 1;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(v7 + 1616))(v9, a3, v8);
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned __int8 **, _QWORD))(WdfFunctions_01015 + 2152))(
          WdfDriverGlobals,
          a3,
          2,
          &v23,
          0);
  v13 = v11;
  if ( v11 >= 0 )
  {
    v15 = *v23;
    if ( (unsigned __int8)v15 < *(_BYTE *)(a1 + 128) )
    {
      v16 = v23[1];
      v17 = (v16 & 0xF) + 16LL;
      if ( v16 >= 0 )
        v17 = v23[1] & 0xF;
      v18 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8 * (35 * v15 + v17) + 24);
      if ( !WinUSB_IsInterruptOrBulkOutPipe(v18) )
      {
        v13 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v13;
        LOBYTE(v19) = 3;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          3,
          24,
          (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
          v16);
        goto LABEL_23;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 4;
        WPP_RECORDER_SF_dD(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          5,
          27,
          (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
          v16,
          *(_DWORD *)(v10 + 28));
      }
      v20 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2248))(
              WdfDriverGlobals,
              a3,
              *(_QWORD *)(v18 + 48));
      v13 = v20;
      if ( v20 >= 0 )
      {
        *a4 = 0;
        goto LABEL_23;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v13;
      v14 = 28;
      v22 = v20;
    }
    else
    {
      v13 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v13;
      v14 = 22;
      v22 = 13;
    }
    LOBYTE(v12) = 2;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v13;
    v14 = 21;
    v22 = v11;
    LOBYTE(v12) = 3;
  }
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    v12,
    3,
    v14,
    (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
    v22);
LABEL_23:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      29,
      (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x14000b3fc  mov     rax, rsp
0x14000b3ff  mov     [rax+10h], rdx
0x14000b403  push    rbx
0x14000b404  push    rbp
0x14000b405  push    rsi
0x14000b406  push    rdi
0x14000b407  push    r12
0x14000b409  push    r13
0x14000b40b  push    r14
0x14000b40d  push    r15
0x14000b40f  sub     rsp, 48h
0x14000b413  xor     edi, edi
0x14000b415  mov     r14, r9
0x14000b418  mov     [rax+10h], rdi
0x14000b41c  mov     rbp, r8
0x14000b41f  mov     rsi, rcx
0x14000b422  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b429  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000b430  lea     r13, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b437  jz      short loc_14000B45D
0x14000b439  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b440  cmp     [rcx+48h], di
0x14000b444  jz      short loc_14000B45D
0x14000b446  mov     rcx, [rcx+40h]
0x14000b44a  lea     r9d, [rdi+14h]
0x14000b44e  lea     r8d, [rdi+1]
0x14000b452  mov     [rax-68h], r13
0x14000b456  mov     dl, 5
0x14000b458  call    WPP_RECORDER_SF_
0x14000b45d  mov     rax, cs:WdfFunctions_01015
0x14000b464  mov     rdx, rbp
0x14000b467  mov     r8, cs:off_140015040
0x14000b46e  mov     rcx, cs:WdfDriverGlobals
0x14000b475  mov     byte ptr [r14], 1
0x14000b479  mov     rax, [rax+650h]
0x14000b480  call    _guard_dispatch_icall
0x14000b485  mov     rcx, cs:WdfFunctions_01015
0x14000b48c  lea     r9, [rsp+88h+arg_8]
0x14000b494  mov     r15, rax
0x14000b497  mov     [rsp+88h+var_68], rdi
0x14000b49c  mov     r8d, 2
0x14000b4a2  mov     rdx, rbp
0x14000b4a5  mov     rax, [rcx+868h]
0x14000b4ac  mov     rcx, cs:WdfDriverGlobals
0x14000b4b3  call    _guard_dispatch_icall
0x14000b4b8  mov     ebx, eax
0x14000b4ba  test    eax, eax
0x14000b4bc  jns     short loc_14000B4F6
0x14000b4be  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000b4c5  jz      loc_14000B64D
0x14000b4cb  mov     r9d, 15h
0x14000b4d1  mov     dword ptr [rsp+88h+var_60], eax
0x14000b4d5  lea     r8d, [r9-12h]
0x14000b4d9  mov     dl, r8b
0x14000b4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4e3  mov     [rsp+88h+var_68], r13
0x14000b4e8  mov     rcx, [rcx+40h]
0x14000b4ec  call    WPP_RECORDER_SF_d
0x14000b4f1  jmp     loc_14000B619
0x14000b4f6  mov     rax, [rsp+88h+arg_8]
0x14000b4fe  movzx   r8d, byte ptr [rax]
0x14000b502  cmp     r8b, [rsi+80h]
0x14000b509  jb      short loc_14000B531
0x14000b50b  mov     ebx, 0C000000Dh
0x14000b510  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000b517  jz      loc_14000B64D
0x14000b51d  mov     r9d, 16h
0x14000b523  mov     dword ptr [rsp+88h+var_60], ebx
0x14000b527  mov     r8d, 3
0x14000b52d  mov     dl, 2
0x14000b52f  jmp     short loc_14000B4DC
0x14000b531  movzx   ecx, byte ptr [rax+1]
0x14000b535  mov     edi, ecx
0x14000b537  mov     eax, edi
0x14000b539  and     eax, 0Fh
0x14000b53c  test    cl, cl
0x14000b53e  lea     rdx, [rax+10h]
0x14000b542  cmovns  rdx, rax
0x14000b546  mov     rax, [rsi+88h]
0x14000b54d  imul    rcx, r8, 23h ; '#'
0x14000b551  add     rdx, rcx
0x14000b554  mov     rbx, [rax+rdx*8+18h]
0x14000b559  mov     rcx, rbx
0x14000b55c  call    WinUSB_IsInterruptOrBulkOutPipe
0x14000b561  test    al, al
0x14000b563  jnz     short loc_14000B5A1
0x14000b565  mov     ebx, 0C000000Dh
0x14000b56a  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000b571  jz      loc_14000B64D
0x14000b577  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b57e  mov     r9d, 18h
0x14000b584  mov     dword ptr [rsp+88h+var_60], edi
0x14000b588  mov     [rsp+88h+var_68], r13
0x14000b58d  mov     rcx, [rcx+40h]
0x14000b591  lea     r8d, [r9-15h]
0x14000b595  mov     dl, r8b
0x14000b598  call    WPP_RECORDER_SF_d
0x14000b59d  xor     edi, edi
0x14000b59f  jmp     short loc_14000B619
0x14000b5a1  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000b5a8  jz      short loc_14000B5D7
0x14000b5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5b1  mov     r9d, 1Bh
0x14000b5b7  mov     eax, [r15+1Ch]
0x14000b5bb  mov     dl, 4
0x14000b5bd  mov     [rsp+88h+var_58], eax
0x14000b5c1  mov     dword ptr [rsp+88h+var_60], edi
0x14000b5c5  mov     rcx, [rcx+40h]
0x14000b5c9  lea     r8d, [r9-16h]
0x14000b5cd  mov     [rsp+88h+var_68], r13
0x14000b5d2  call    WPP_RECORDER_SF_dD
0x14000b5d7  mov     rax, cs:WdfFunctions_01015
0x14000b5de  mov     rdx, rbp
0x14000b5e1  mov     r8, [rbx+30h]
0x14000b5e5  mov     rcx, cs:WdfDriverGlobals
0x14000b5ec  mov     rax, [rax+8C8h]
0x14000b5f3  call    _guard_dispatch_icall
0x14000b5f8  xor     edi, edi
0x14000b5fa  mov     ebx, eax
0x14000b5fc  test    eax, eax
0x14000b5fe  jns     short loc_14000B616
0x14000b600  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000b607  jz      short loc_14000B64D
0x14000b609  lea     r9d, [rdi+1Ch]
0x14000b60d  mov     dword ptr [rsp+88h+var_60], eax
0x14000b611  jmp     loc_14000B527
0x14000b616  mov     [r14], dil
0x14000b619  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000b620  jz      short loc_14000B64D
0x14000b622  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b629  cmp     [rcx+48h], di
0x14000b62d  jz      short loc_14000B64D
0x14000b62f  mov     rcx, [rcx+40h]
0x14000b633  mov     r9d, 1Dh
0x14000b639  mov     dword ptr [rsp+88h+var_60], ebx
0x14000b63d  mov     dl, 5
0x14000b63f  mov     [rsp+88h+var_68], r13
0x14000b644  lea     r8d, [r9-1Ch]
0x14000b648  call    WPP_RECORDER_SF_d
0x14000b64d  mov     eax, ebx
0x14000b64f  add     rsp, 48h
0x14000b653  pop     r15
0x14000b655  pop     r14
0x14000b657  pop     r13
0x14000b659  pop     r12
0x14000b65b  pop     rdi
0x14000b65c  pop     rsi
0x14000b65d  pop     rbp
0x14000b65e  pop     rbx
0x14000b65f  retn
```
