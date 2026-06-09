# WinUSB_RawIoReadCompletion

- ea: `0x1400093e0`
- end: `0x14000962e`
- name: `WinUSB_RawIoReadCompletion`
- size: `590`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000264c`
- `0x1400062f4`
- `0x140006cb0`
- `0x14000866c`
- `0x1400093e0`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUSB_RawIoReadCompletion(__int64 a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  bool v8; // si
  __int64 *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rbp
  __int64 v13; // r12
  __int64 result; // rax
  int v15; // edx
  __int64 v16; // rcx
  int v17; // r8d
  unsigned int v18; // ebx
  char v19; // cl
  char v20; // cl

  v8 = 1;
  v9 = WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      1,
      10,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids);
  }
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1392))(WdfDriverGlobals, a2);
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          v10,
          off_1400150F0);
  WinUSB_DecrementKeepAliveCount(v11, a1);
  v12 = *((unsigned __int8 *)a4 + 24);
  v13 = *(_QWORD *)(*(_QWORD *)(v11 + 136) + 8 * (v12 + 35LL * *((unsigned __int8 *)a4 + 25)) + 24);
  *a4 += *(_DWORD *)(*(_QWORD *)(a3 + 24) + 16LL);
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, a1);
  v18 = result;
  if ( (int)result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = v12 & 0xF;
      if ( (v12 & 0x10) != 0 )
        v19 += 0x80;
      LOBYTE(v15) = 3;
      result = WPP_RECORDER_SF_dDd(
                 WPP_GLOBAL_Control->DeviceExtension,
                 v15,
                 4,
                 11,
                 (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
                 v19,
                 a4[7],
                 result);
    }
    if ( v18 != -1073741536 && v18 != -1073741667 && *((_BYTE *)a4 + 13) )
    {
      result = WinUSB_HandlePipeError(v16, v13, a1);
      v18 = result;
      v8 = (int)result < 0;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v20 = v12 & 0xF;
    if ( (v12 & 0x10) != 0 )
      v20 += 0x80;
    result = WPP_RECORDER_SF_dDdd(
               WPP_GLOBAL_Control->DeviceExtension,
               v15,
               v17,
               12,
               (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
               v20,
               a4[7],
               a4[1],
               *a4);
  }
  if ( v8 )
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
               WdfDriverGlobals,
               a1,
               v18,
               *a4);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v15) = 5;
      return WPP_RECORDER_SF_d(
               WPP_GLOBAL_Control->DeviceExtension,
               v15,
               1,
               13,
               (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
               v18);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400093e0  push    rbx
0x1400093e2  push    rbp
0x1400093e3  push    rsi
0x1400093e4  push    rdi
0x1400093e5  push    r12
0x1400093e7  push    r13
0x1400093e9  push    r14
0x1400093eb  push    r15
0x1400093ed  sub     rsp, 58h
0x1400093f1  mov     rdi, r9
0x1400093f4  mov     r15, r8
0x1400093f7  mov     rbx, rdx
0x1400093fa  mov     r14, rcx
0x1400093fd  mov     sil, 1
0x140009400  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009407  xor     r13d, r13d
0x14000940a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009411  lea     rdx, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009418  jz      short loc_140009440
0x14000941a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009421  cmp     [rcx+48h], r13w
0x140009426  jz      short loc_140009440
0x140009428  mov     rcx, [rcx+40h]
0x14000942c  lea     r9d, [r13+0Ah]
0x140009430  mov     [rsp+98h+var_78], rdx
0x140009435  lea     r8d, [r13+1]
0x140009439  mov     dl, 5
0x14000943b  call    WPP_RECORDER_SF_
0x140009440  mov     rax, cs:WdfFunctions_01015
0x140009447  mov     rdx, rbx
0x14000944a  mov     rcx, cs:WdfDriverGlobals
0x140009451  mov     rax, [rax+570h]
0x140009458  call    _guard_dispatch_icall
0x14000945d  mov     rcx, cs:WdfFunctions_01015
0x140009464  mov     rdx, rax
0x140009467  mov     r8, cs:off_1400150F0
0x14000946e  mov     rax, [rcx+650h]
0x140009475  mov     rcx, cs:WdfDriverGlobals
0x14000947c  call    _guard_dispatch_icall
0x140009481  mov     rdx, r14
0x140009484  mov     rcx, rax
0x140009487  mov     rbx, rax
0x14000948a  call    WinUSB_DecrementKeepAliveCount
0x14000948f  movzx   ecx, byte ptr [rdi+19h]
0x140009493  mov     rax, [rbx+88h]
0x14000949a  movzx   ebp, byte ptr [rdi+18h]
0x14000949e  imul    rdx, rcx, 23h ; '#'
0x1400094a2  add     rdx, rbp
0x1400094a5  mov     r12, [rax+rdx*8+18h]
0x1400094aa  mov     rdx, r14
0x1400094ad  mov     rax, [r15+18h]
0x1400094b1  mov     ecx, [rax+10h]
0x1400094b4  add     [rdi], ecx
0x1400094b6  mov     rax, cs:WdfFunctions_01015
0x1400094bd  mov     rcx, cs:WdfDriverGlobals
0x1400094c4  mov     rax, [rax+7F0h]
0x1400094cb  call    _guard_dispatch_icall
0x1400094d0  mov     ebx, eax
0x1400094d2  test    eax, eax
0x1400094d4  jns     loc_14000955E
0x1400094da  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400094e1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400094e8  jz      short loc_14000952F
0x1400094ea  mov     ecx, ebp
0x1400094ec  and     ecx, 0Fh
0x1400094ef  test    bpl, 10h
0x1400094f3  jz      short loc_1400094F8
0x1400094f5  sub     ecx, 0FFFFFF80h
0x1400094f8  mov     eax, [rdi+1Ch]
0x1400094fb  mov     r9d, 0Bh
0x140009501  mov     [rsp+98h+var_60], ebx
0x140009505  mov     dl, 3
0x140009507  mov     [rsp+98h+var_68], eax
0x14000950b  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009512  mov     [rsp+98h+var_70], ecx
0x140009516  mov     rcx, cs:WPP_GLOBAL_Control
0x14000951d  lea     r8d, [r9-7]
0x140009521  mov     [rsp+98h+var_78], rax
0x140009526  mov     rcx, [rcx+40h]
0x14000952a  call    WPP_RECORDER_SF_dDd
0x14000952f  cmp     ebx, 0C0000120h
0x140009535  jz      short loc_140009565
0x140009537  cmp     ebx, 0C000009Dh
0x14000953d  jz      short loc_140009565
0x14000953f  cmp     [rdi+0Dh], r13b
0x140009543  jz      short loc_140009565
0x140009545  mov     r8, r14
0x140009548  mov     rdx, r12
0x14000954b  call    WinUSB_HandlePipeError
0x140009550  test    eax, eax
0x140009552  movzx   esi, sil
0x140009556  mov     ebx, eax
0x140009558  cmovns  esi, r13d
0x14000955c  jmp     short loc_140009565
0x14000955e  lea     r15, WPP_RECORDER_INITIALIZED
0x140009565  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000956c  jz      short loc_1400095B8
0x14000956e  mov     ecx, ebp
0x140009570  and     ecx, 0Fh
0x140009573  test    bpl, 10h
0x140009577  jz      short loc_14000957C
0x140009579  sub     ecx, 0FFFFFF80h
0x14000957c  mov     eax, [rdi]
0x14000957e  lea     rbp, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009585  mov     [rsp+98h+var_58], eax
0x140009589  mov     r9d, 0Ch
0x14000958f  mov     eax, [rdi+4]
0x140009592  mov     [rsp+98h+var_60], eax
0x140009596  mov     eax, [rdi+1Ch]
0x140009599  mov     [rsp+98h+var_68], eax
0x14000959d  mov     [rsp+98h+var_70], ecx
0x1400095a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095a8  mov     [rsp+98h+var_78], rbp
0x1400095ad  mov     rcx, [rcx+40h]
0x1400095b1  call    WPP_RECORDER_SF_dDdd
0x1400095b6  jmp     short loc_1400095BF
0x1400095b8  lea     rbp, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x1400095bf  test    sil, sil
0x1400095c2  jz      short loc_1400095E7
0x1400095c4  mov     rax, cs:WdfFunctions_01015
0x1400095cb  mov     r8d, ebx
0x1400095ce  mov     r9d, [rdi]
0x1400095d1  mov     rdx, r14
0x1400095d4  mov     rcx, cs:WdfDriverGlobals
0x1400095db  mov     rax, [rax+848h]
0x1400095e2  call    _guard_dispatch_icall
0x1400095e7  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400095ee  jz      short loc_14000961C
0x1400095f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095f7  cmp     [rcx+48h], r13w
0x1400095fc  jz      short loc_14000961C
0x1400095fe  mov     rcx, [rcx+40h]
0x140009602  mov     r9d, 0Dh
0x140009608  mov     [rsp+98h+var_70], ebx
0x14000960c  mov     dl, 5
0x14000960e  mov     [rsp+98h+var_78], rbp
0x140009613  lea     r8d, [r9-0Ch]
0x140009617  call    WPP_RECORDER_SF_d
0x14000961c  add     rsp, 58h
0x140009620  pop     r15
0x140009622  pop     r14
0x140009624  pop     r13
0x140009626  pop     r12
0x140009628  pop     rdi
0x140009629  pop     rsi
0x14000962a  pop     rbp
0x14000962b  pop     rbx
0x14000962c  retn
```
