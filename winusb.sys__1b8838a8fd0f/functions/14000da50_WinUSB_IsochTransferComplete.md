# WinUSB_IsochTransferComplete

- ea: `0x14000da50`
- end: `0x14000dcc4`
- name: `WinUSB_IsochTransferComplete`
- size: `628`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000bc4c`
- `0x14000c948`
- `0x14000da50`
- `0x14000fe14`
- `0x140010700`
- `0x1400108c0`

## pseudocode

```c
__int64 __fastcall WinUSB_IsochTransferComplete(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v7; // rbp
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(PWDF_DRIVER_GLOBALS, __int64, __int64 *); // rax
  int v10; // edi
  __int64 v11; // rax
  int v12; // edx
  int v13; // r8d
  __int64 v14; // rbx
  unsigned int v15; // edx
  unsigned int i; // esi
  void *v17; // rcx
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-58h]
  __int64 v20; // [rsp+90h] [rbp+18h] BYREF
  __int64 v21; // [rsp+98h] [rbp+20h]

  v20 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      62,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  v7 = *a4;
  v8 = a4[1];
  v9 = *(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1552);
  v10 = *(_DWORD *)(a3 + 8);
  v21 = *a4;
  v11 = v9(WdfDriverGlobals, v8, &v20);
  v14 = v11;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDD(WPP_GLOBAL_Control->DeviceExtension, v12, v13, 63, v19, a1, v10, *(_DWORD *)(v11 + 4));
  if ( v10 >= 0 )
  {
    v15 = *(_DWORD *)(v14 + 132);
    if ( v15 )
    {
      for ( i = 0; i < v15; ++i )
      {
        if ( *(int *)(v14 + 12LL * i + 148) < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v15) = 4;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v15,
              3,
              64,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              *(_DWORD *)(v14 + 12LL * i + 148));
            v15 = *(_DWORD *)(v14 + 132);
          }
          v10 = -1073741823;
        }
      }
      v7 = v21;
    }
  }
  v17 = (void *)a4[10];
  if ( v17 )
    memmove(v17, (const void *)(v14 + 140), 12LL * *(unsigned int *)(v14 + 132));
  _InterlockedAdd((volatile signed __int32 *)(v7 + 200), -*((_DWORD *)a4 + 10));
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a4[1]);
  a4[1] = 0;
  WinUSB_UnmapIsochBuffer(a4);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01015 + 2120))(
    WdfDriverGlobals,
    a1,
    (unsigned int)v10,
    a4[11]);
  if ( v10 == -1073741632 || v10 == -1073741810 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        3,
        65,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, _QWORD))(WdfFunctions_01015 + 1320))(
               WdfDriverGlobals,
               *(_QWORD *)(v7 + 192),
               0,
               0);
  }
  else
  {
    result = WinUSB_DispatchIsochRequests(v7);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      return WPP_RECORDER_SF_(
               WPP_GLOBAL_Control->DeviceExtension,
               5,
               1,
               66,
               (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000da50  mov     rax, rsp
0x14000da53  mov     [rax+8], rbx
0x14000da57  push    rbp
0x14000da58  push    rsi
0x14000da59  push    rdi
0x14000da5a  push    r12
0x14000da5c  push    r13
0x14000da5e  push    r14
0x14000da60  push    r15
0x14000da62  sub     rsp, 40h
0x14000da66  xor     r12d, r12d
0x14000da69  mov     r14, r9
0x14000da6c  mov     [rax+18h], r12
0x14000da70  mov     rdi, r8
0x14000da73  mov     r15, rcx
0x14000da76  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000da7d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000da84  lea     rsi, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000da8b  jz      short loc_14000DAB4
0x14000da8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da94  cmp     [rcx+48h], r12w
0x14000da99  jz      short loc_14000DAB4
0x14000da9b  mov     rcx, [rcx+40h]
0x14000da9f  lea     r9d, [r12+3Eh]
0x14000daa4  lea     r8d, [r12+1]
0x14000daa9  mov     [rax-58h], rsi
0x14000daad  mov     dl, 5
0x14000daaf  call    WPP_RECORDER_SF_
0x14000dab4  mov     rax, cs:WdfFunctions_01015
0x14000dabb  lea     r8, [rsp+78h+arg_10]
0x14000dac3  mov     rbp, [r14]
0x14000dac6  mov     rdx, [r14+8]
0x14000daca  mov     rcx, cs:WdfDriverGlobals
0x14000dad1  mov     rax, [rax+610h]
0x14000dad8  mov     edi, [rdi+8]
0x14000dadb  mov     [rsp+78h+arg_18], rbp
0x14000dae3  call    _guard_dispatch_icall
0x14000dae8  mov     rbx, rax
0x14000daeb  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000daf2  jz      short loc_14000DB1A
0x14000daf4  mov     ecx, [rax+4]
0x14000daf7  mov     r9d, 3Fh ; '?'
0x14000dafd  mov     [rsp+78h+var_40], ecx
0x14000db01  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db08  mov     [rsp+78h+var_48], edi
0x14000db0c  mov     [rsp+78h+var_50], r15
0x14000db11  mov     rcx, [rcx+40h]
0x14000db15  call    WPP_RECORDER_SF_qDD
0x14000db1a  test    edi, edi
0x14000db1c  js      short loc_14000DB91
0x14000db1e  mov     edx, [rbx+84h]
0x14000db24  test    edx, edx
0x14000db26  jz      short loc_14000DB91
0x14000db28  mov     esi, r12d
0x14000db2b  lea     rbp, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000db32  mov     eax, esi
0x14000db34  lea     rcx, [rax+rax*2]
0x14000db38  mov     eax, [rbx+rcx*4+94h]
0x14000db3f  test    eax, eax
0x14000db41  jns     short loc_14000DB7C
0x14000db43  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000db4a  jz      short loc_14000DB77
0x14000db4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db53  mov     r9d, 40h ; '@'
0x14000db59  mov     dword ptr [rsp+78h+var_50], eax
0x14000db5d  mov     dl, 4
0x14000db5f  mov     [rsp+78h+var_58], rbp
0x14000db64  mov     rcx, [rcx+40h]
0x14000db68  lea     r8d, [r9-3Dh]
0x14000db6c  call    WPP_RECORDER_SF_d
0x14000db71  mov     edx, [rbx+84h]
0x14000db77  mov     edi, 0C0000001h
0x14000db7c  inc     esi
0x14000db7e  cmp     esi, edx
0x14000db80  jb      short loc_14000DB32
0x14000db82  mov     rbp, [rsp+78h+arg_18]
0x14000db8a  lea     rsi, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000db91  mov     rcx, [r14+50h]; void *
0x14000db95  test    rcx, rcx
0x14000db98  jz      short loc_14000DBB4
0x14000db9a  mov     eax, [rbx+84h]
0x14000dba0  lea     rdx, [rbx+8Ch]; Src
0x14000dba7  lea     r8, [rax+rax*2]
0x14000dbab  shl     r8, 2; Size
0x14000dbaf  call    memmove
0x14000dbb4  mov     eax, [r14+28h]
0x14000dbb8  neg     eax
0x14000dbba  lock add [rbp+0C8h], eax
0x14000dbc1  mov     rax, cs:WdfFunctions_01015
0x14000dbc8  mov     rdx, [r14+8]
0x14000dbcc  mov     rcx, cs:WdfDriverGlobals
0x14000dbd3  mov     rax, [rax+680h]
0x14000dbda  call    _guard_dispatch_icall
0x14000dbdf  mov     rcx, r14
0x14000dbe2  mov     [r14+8], r12
0x14000dbe6  call    WinUSB_UnmapIsochBuffer
0x14000dbeb  mov     rax, cs:WdfFunctions_01015
0x14000dbf2  mov     r8d, edi
0x14000dbf5  mov     r9, [r14+58h]
0x14000dbf9  mov     rdx, r15
0x14000dbfc  mov     rcx, cs:WdfDriverGlobals
0x14000dc03  mov     rax, [rax+848h]
0x14000dc0a  call    _guard_dispatch_icall
0x14000dc0f  cmp     edi, 0C00000C0h
0x14000dc15  jz      short loc_14000DC29
0x14000dc17  cmp     edi, 0C000000Eh
0x14000dc1d  jz      short loc_14000DC29
0x14000dc1f  mov     rcx, rbp
0x14000dc22  call    WinUSB_DispatchIsochRequests
0x14000dc27  jmp     short loc_14000DC7A
0x14000dc29  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000dc30  jz      short loc_14000DC53
0x14000dc32  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc39  mov     r9d, 41h ; 'A'
0x14000dc3f  mov     dl, 4
0x14000dc41  mov     [rsp+78h+var_58], rsi
0x14000dc46  mov     rcx, [rcx+40h]
0x14000dc4a  lea     r8d, [r9-3Eh]
0x14000dc4e  call    WPP_RECORDER_SF_
0x14000dc53  mov     rax, cs:WdfFunctions_01015
0x14000dc5a  xor     r9d, r9d
0x14000dc5d  mov     rdx, [rbp+0C0h]
0x14000dc64  xor     r8d, r8d
0x14000dc67  mov     rcx, cs:WdfDriverGlobals
0x14000dc6e  mov     rax, [rax+528h]
0x14000dc75  call    _guard_dispatch_icall
0x14000dc7a  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000dc81  jz      short loc_14000DCAB
0x14000dc83  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc8a  cmp     [rcx+48h], r12w
0x14000dc8f  jz      short loc_14000DCAB
0x14000dc91  mov     rcx, [rcx+40h]
0x14000dc95  mov     r9d, 42h ; 'B'
0x14000dc9b  mov     dl, 5
0x14000dc9d  mov     [rsp+78h+var_58], rsi
0x14000dca2  lea     r8d, [r9-41h]
0x14000dca6  call    WPP_RECORDER_SF_
0x14000dcab  mov     rbx, [rsp+78h+arg_0]
0x14000dcb3  add     rsp, 40h
0x14000dcb7  pop     r15
0x14000dcb9  pop     r14
0x14000dcbb  pop     r13
0x14000dcbd  pop     r12
0x14000dcbf  pop     rdi
0x14000dcc0  pop     rsi
0x14000dcc1  pop     rbp
0x14000dcc2  retn
```
