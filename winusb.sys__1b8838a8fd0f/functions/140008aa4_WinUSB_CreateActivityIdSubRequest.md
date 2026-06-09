# WinUSB_CreateActivityIdSubRequest

- ea: `0x140008aa4`
- end: `0x140008d03`
- name: `WinUSB_CreateActivityIdSubRequest`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000a450`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x140008aa4`
- `0x1400106c0`
- `0x140010700`

## pseudocode

```c
__int64 *__fastcall WinUSB_CreateActivityIdSubRequest(unsigned __int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 v6; // rbx
  __int64 *result; // rax
  __int64 v9; // rax
  char v10; // bl
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // [rsp+30h] [rbp-39h] BYREF
  _OWORD v14[2]; // [rsp+38h] [rbp-31h] BYREF
  __int128 v15; // [rsp+58h] [rbp-11h]
  __int64 *v16; // [rsp+68h] [rbp-1h]
  __int128 v17; // [rsp+70h] [rbp+7h] BYREF

  LODWORD(v16) = 0;
  v13 = 0;
  v6 = a2;
  v17 = 0;
  memset(v14, 0, sizeof(v14));
  v15 = 0;
  result = WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    result = (__int64 *)WPP_RECORDER_SF_(
                          WPP_GLOBAL_Control->DeviceExtension,
                          a2,
                          1,
                          48,
                          (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids);
  }
  if ( WPP_MAIN_CB.Queue.ListEntry.Blink && WPP_MAIN_CB.Queue.Wcb.DeviceRoutine )
  {
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2280))(WdfDriverGlobals, v6);
    result = (__int64 *)((__int64 (__fastcall *)(__int64, __int128 *))WPP_MAIN_CB.Queue.Wcb.DeviceRoutine)(v9, &v17);
    v10 = (char)result;
    if ( (int)result >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2280))(WdfDriverGlobals, *a3);
      result = (__int64 *)((__int64 (__fastcall *)(__int64, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Blink)(v11, &v17);
      v10 = (char)result;
      if ( (int)result < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 4;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            4,
            49,
            (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids);
        }
        v16 = off_140015040;
        memset((char *)v14 + 4, 0, 20);
        LODWORD(v14[0]) = 56;
        *((_QWORD *)&v14[1] + 1) = 0x100000001LL;
        v15 = a1;
        result = (__int64 *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _OWORD *, __int64, __int64 *))(WdfFunctions_01015 + 1976))(
                              WdfDriverGlobals,
                              v14,
                              a4,
                              &v13);
        v10 = (char)result;
        if ( (int)result >= 0 )
        {
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, *a3);
          *a3 = v13;
          v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2280))(WdfDriverGlobals);
          result = (__int64 *)((__int64 (__fastcall *)(__int64, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Blink)(
                                v12,
                                &v17);
        }
      }
    }
  }
  else
  {
    v10 = -69;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      return (__int64 *)WPP_RECORDER_SF_d(
                          WPP_GLOBAL_Control->DeviceExtension,
                          a2,
                          1,
                          50,
                          (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
                          v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008aa4  push    rbp
0x140008aa6  push    rbx
0x140008aa7  push    rsi
0x140008aa8  push    rdi
0x140008aa9  push    r13
0x140008aab  push    r14
0x140008aad  push    r15
0x140008aaf  lea     rbp, [rsp-27h]
0x140008ab4  sub     rsp, 90h
0x140008abb  mov     rax, cs:__security_cookie
0x140008ac2  xor     rax, rsp
0x140008ac5  mov     [rbp+57h+var_40], rax
0x140008ac9  xorps   xmm0, xmm0
0x140008acc  xor     eax, eax
0x140008ace  xor     r15d, r15d
0x140008ad1  mov     dword ptr [rbp+57h+var_58], eax
0x140008ad4  mov     [rbp+57h+var_90], r15
0x140008ad8  mov     r14, r9
0x140008adb  mov     rdi, r8
0x140008ade  mov     rbx, rdx
0x140008ae1  mov     rsi, rcx
0x140008ae4  movups  [rbp+57h+var_50], xmm0
0x140008ae8  movups  [rbp+57h+var_88], xmm0
0x140008aec  movups  [rbp+57h+var_78], xmm0
0x140008af0  movups  [rbp+57h+var_68], xmm0
0x140008af4  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140008afb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140008b02  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140008b09  jz      short loc_140008B31
0x140008b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b12  cmp     [rcx+48h], r15w
0x140008b17  jz      short loc_140008B31
0x140008b19  mov     rcx, [rcx+40h]
0x140008b1d  lea     r9d, [r15+30h]
0x140008b21  lea     r8d, [r15+1]
0x140008b25  mov     [rsp+0C0h+var_A0], rax
0x140008b2a  mov     dl, 5
0x140008b2c  call    WPP_RECORDER_SF_
0x140008b31  cmp     qword ptr cs:WPP_MAIN_CB.Queue+8, r15
0x140008b38  jz      loc_140008CA3
0x140008b3e  cmp     qword ptr cs:WPP_MAIN_CB.Queue+18h, r15
0x140008b45  jz      loc_140008CA3
0x140008b4b  mov     rax, cs:WdfFunctions_01015
0x140008b52  mov     rdx, rbx
0x140008b55  mov     rcx, cs:WdfDriverGlobals
0x140008b5c  mov     rax, [rax+8E8h]
0x140008b63  call    _guard_dispatch_icall
0x140008b68  mov     rcx, rax
0x140008b6b  lea     rdx, [rbp+57h+var_50]
0x140008b6f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x140008b76  call    _guard_dispatch_icall
0x140008b7b  mov     ebx, eax
0x140008b7d  test    eax, eax
0x140008b7f  js      loc_140008CA8
0x140008b85  mov     rax, cs:WdfFunctions_01015
0x140008b8c  mov     rdx, [rdi]
0x140008b8f  mov     rcx, cs:WdfDriverGlobals
0x140008b96  mov     rax, [rax+8E8h]
0x140008b9d  call    _guard_dispatch_icall
0x140008ba2  mov     rcx, rax
0x140008ba5  lea     rdx, [rbp+57h+var_50]
0x140008ba9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008bb0  call    _guard_dispatch_icall
0x140008bb5  mov     ebx, eax
0x140008bb7  test    eax, eax
0x140008bb9  jns     loc_140008CA8
0x140008bbf  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140008bc6  jz      short loc_140008BF1
0x140008bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bcf  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140008bd6  mov     r9d, 31h ; '1'
0x140008bdc  mov     [rsp+0C0h+var_A0], rax
0x140008be1  mov     rcx, [rcx+40h]
0x140008be5  lea     r8d, [r9-2Dh]
0x140008be9  mov     dl, r8b
0x140008bec  call    WPP_RECORDER_SF_
0x140008bf1  mov     rax, cs:off_140015040
0x140008bf8  lea     r9, [rbp+57h+var_90]
0x140008bfc  mov     rcx, cs:WdfDriverGlobals
0x140008c03  lea     rdx, [rbp+57h+var_88]
0x140008c07  mov     [rbp+57h+var_58], rax
0x140008c0b  xorps   xmm0, xmm0
0x140008c0e  mov     rax, cs:WdfFunctions_01015
0x140008c15  mov     r8, r14
0x140008c18  movdqu  [rbp+57h+var_88+4], xmm0
0x140008c1d  mov     dword ptr [rbp+57h+var_78+4], r15d
0x140008c21  mov     qword ptr [rbp+57h+var_68+8], r15
0x140008c25  mov     dword ptr [rbp+57h+var_88], 38h ; '8'
0x140008c2c  mov     dword ptr [rbp+57h+var_78+8], 1
0x140008c33  mov     dword ptr [rbp+57h+var_78+0Ch], 1
0x140008c3a  mov     qword ptr [rbp+57h+var_68], rsi
0x140008c3e  mov     rax, [rax+7B8h]
0x140008c45  call    _guard_dispatch_icall
0x140008c4a  mov     ebx, eax
0x140008c4c  test    eax, eax
0x140008c4e  js      short loc_140008CA8
0x140008c50  mov     rax, cs:WdfFunctions_01015
0x140008c57  mov     rdx, [rdi]
0x140008c5a  mov     rcx, cs:WdfDriverGlobals
0x140008c61  mov     rax, [rax+680h]
0x140008c68  call    _guard_dispatch_icall
0x140008c6d  mov     rdx, [rbp+57h+var_90]
0x140008c71  mov     [rdi], rdx
0x140008c74  mov     rax, cs:WdfFunctions_01015
0x140008c7b  mov     rcx, cs:WdfDriverGlobals
0x140008c82  mov     rax, [rax+8E8h]
0x140008c89  call    _guard_dispatch_icall
0x140008c8e  mov     rcx, rax
0x140008c91  lea     rdx, [rbp+57h+var_50]
0x140008c95  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008c9c  call    _guard_dispatch_icall
0x140008ca1  jmp     short loc_140008CA8
0x140008ca3  mov     ebx, 0C00000BBh
0x140008ca8  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140008caf  jz      short loc_140008CE4
0x140008cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140008cb8  cmp     [rcx+48h], r15w
0x140008cbd  jz      short loc_140008CE4
0x140008cbf  mov     rcx, [rcx+40h]
0x140008cc3  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140008cca  mov     r9d, 32h ; '2'
0x140008cd0  mov     [rsp+0C0h+var_98], ebx
0x140008cd4  mov     dl, 5
0x140008cd6  mov     [rsp+0C0h+var_A0], rax
0x140008cdb  lea     r8d, [r9-31h]
0x140008cdf  call    WPP_RECORDER_SF_d
0x140008ce4  mov     rcx, [rbp+57h+var_40]
0x140008ce8  xor     rcx, rsp; StackCookie
0x140008ceb  call    __security_check_cookie
0x140008cf0  add     rsp, 90h
0x140008cf7  pop     r15
0x140008cf9  pop     r14
0x140008cfb  pop     r13
0x140008cfd  pop     rdi
0x140008cfe  pop     rsi
0x140008cff  pop     rbx
0x140008d00  pop     rbp
0x140008d01  retn
```
