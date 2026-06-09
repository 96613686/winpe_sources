# AttachSubclassHeader(HWND__ *)

- ea: `0x180039fe8`
- end: `0x18003a176`
- name: `?AttachSubclassHeader@@YAPEAUSUBCLASS_HEADER@@PEAUHWND__@@@Z`
- size: `398`
- prototype: `struct SUBCLASS_HEADER *__fastcall(HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039860`

## callees

- `0x180039640`
- `0x180039fe8`
- `0x18008cc70`
- `0x18008df70`
- `0x180093204`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a091`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a06c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a06c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a00b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a00b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18003a02f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18003a02f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18003a0ef`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18003a0ef`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18003a088`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18003a088`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18003a003`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18003a003`

## pseudocode

```c
struct SUBCLASS_HEADER *__fastcall AttachSubclassHeader(HWND a1)
{
  _DWORD *PropW; // rbx
  DWORD WindowThreadProcessId; // esi
  struct SUBCLASS_HEADER *v5; // rax
  LONG_PTR v6; // r14
  DWORD LastError; // eax
  char v8; // di
  bool v9; // si
  bool v10; // r15
  __int64 (__fastcall *WindowLongPtrW)(HWND, unsigned int, unsigned __int64, __int64); // rax
  bool v12; // [rsp+40h] [rbp-18h] BYREF
  char v13; // [rsp+41h] [rbp-17h] BYREF
  DWORD v14[5]; // [rsp+44h] [rbp-14h] BYREF
  HWND v15; // [rsp+90h] [rbp+38h] BYREF
  bool v16; // [rsp+98h] [rbp+40h] BYREF
  bool v17; // [rsp+A0h] [rbp+48h] BYREF
  bool v18; // [rsp+A8h] [rbp+50h] BYREF

  v15 = a1;
  PropW = 0;
  WindowThreadProcessId = GetWindowThreadProcessId(a1, 0);
  if ( WindowThreadProcessId == GetCurrentThreadId() )
  {
    PropW = GetPropW(a1, L"SHCore.Subclass.Data");
    if ( !PropW )
    {
      v5 = ReAllocSubclassHeader(a1, 0, 2u);
      PropW = v5;
      if ( v5 )
      {
        *((_DWORD *)v5 + 3) = WindowThreadProcessId;
        v12 = 0;
        v13 = 0;
        v18 = 0;
        v17 = 0;
        v16 = 0;
        SetLastError(0);
        v6 = SetWindowLongPtrW(a1, -4, (LONG_PTR)MasterSubclassProc);
        LastError = GetLastError();
        v14[0] = LastError;
        if ( v6 )
        {
          if ( !PropW[1] )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          *((_QWORD *)PropW + 5) = v6;
          v8 = 1;
          *((_QWORD *)PropW + 4) = 0;
          v9 = MasterSubclassProc == (__int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64))v6;
          v13 = 1;
          LOBYTE(v6) = 0;
          v12 = v9;
          *PropW = 1;
          v10 = 0;
          *((_QWORD *)PropW + 3) = CallOriginalWndProc;
        }
        else
        {
          v6 = LastError != 0;
          v18 = LastError != 0;
          WindowLongPtrW = (__int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64))GetWindowLongPtrW(
                                                                                                    a1,
                                                                                                    -4);
          v17 = WindowLongPtrW == 0;
          v10 = WindowLongPtrW == MasterSubclassProc;
          v16 = WindowLongPtrW == MasterSubclassProc;
          FreeSubclassHeader(a1, (struct SUBCLASS_HEADER *)PropW);
          PropW = 0;
          v8 = 0;
          v9 = 0;
        }
        SHCoreTelemetry::SHSetWindowSubclassAttach<HWND__ * &,bool &,bool &,bool &,unsigned long &,bool &,bool &>(
          (unsigned int)&v15,
          (unsigned int)&v13,
          (unsigned int)&v12,
          (unsigned int)&v18,
          (__int64)v14,
          (__int64)&v17,
          (__int64)&v16);
        if ( !v8 && !(_BYTE)v6 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( v9 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( v10 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
    }
  }
  return (struct SUBCLASS_HEADER *)PropW;
}

```

## disassembly

```asm
0x180039fe8  mov     [rsp-30h+arg_0], rcx
0x180039fed  push    rbp
0x180039fee  push    rbx
0x180039fef  push    rsi
0x180039ff0  push    rdi
0x180039ff1  push    r14
0x180039ff3  push    r15
0x180039ff5  mov     rbp, rsp
0x180039ff8  sub     rsp, 58h
0x180039ffc  xor     edx, edx; lpdwProcessId
0x180039ffe  mov     rdi, rcx
0x18003a001  xor     ebx, ebx
0x18003a003  call    cs:__imp_GetWindowThreadProcessId
0x18003a009  mov     esi, eax
0x18003a00b  call    cs:__imp_GetCurrentThreadId
0x18003a011  cmp     esi, eax
0x18003a013  jz      short loc_18003A025
0x18003a015  mov     rax, rbx
0x18003a018  add     rsp, 58h
0x18003a01c  pop     r15
0x18003a01e  pop     r14
0x18003a020  pop     rdi
0x18003a021  pop     rsi
0x18003a022  pop     rbx
0x18003a023  pop     rbp
0x18003a024  retn
0x18003a025  lea     rdx, aShcoreSubclass_5; "SHCore.Subclass.Data"
0x18003a02c  mov     rcx, rdi; hWnd
0x18003a02f  call    cs:__imp_GetPropW
0x18003a035  mov     rbx, rax
0x18003a038  test    rax, rax
0x18003a03b  jnz     short loc_18003A015
0x18003a03d  xor     edx, edx; Src
0x18003a03f  lea     r8d, [rax+2]; unsigned int
0x18003a043  mov     rcx, rdi; hWnd
0x18003a046  call    ?ReAllocSubclassHeader@@YAPEAUSUBCLASS_HEADER@@PEAUHWND__@@PEAU1@I@Z; ReAllocSubclassHeader(HWND__ *,SUBCLASS_HEADER *,uint)
0x18003a04b  mov     rbx, rax
0x18003a04e  test    rax, rax
0x18003a051  jz      short loc_18003A015
0x18003a053  xor     ecx, ecx; dwErrCode
0x18003a055  mov     [rax+0Ch], esi
0x18003a058  mov     [rbp+var_18], 0
0x18003a05c  mov     [rbp+var_17], 0
0x18003a060  mov     [rbp+arg_18], 0
0x18003a064  mov     [rbp+arg_10], 0
0x18003a068  mov     [rbp+arg_8], 0
0x18003a06c  call    cs:__imp_SetLastError
0x18003a072  lea     rsi, ?MasterSubclassProc@@YA_JPEAUHWND__@@I_K_J@Z; MasterSubclassProc(HWND__ *,uint,unsigned __int64,__int64)
0x18003a079  mov     r15d, 0FFFFFFFCh
0x18003a07f  mov     r8, rsi; dwNewLong
0x18003a082  mov     edx, r15d; nIndex
0x18003a085  mov     rcx, rdi; hWnd
0x18003a088  call    cs:__imp_SetWindowLongPtrW
0x18003a08e  mov     r14, rax
0x18003a091  call    cs:__imp_GetLastError
0x18003a097  mov     [rbp+var_14], eax
0x18003a09a  test    r14, r14
0x18003a09d  jz      short loc_18003A0DF
0x18003a09f  cmp     dword ptr [rbx+4], 0
0x18003a0a3  ja      short loc_18003A0AA
0x18003a0a5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a0aa  cmp     rsi, r14
0x18003a0ad  mov     [rbx+28h], r14
0x18003a0b1  mov     edi, 1
0x18003a0b6  mov     qword ptr [rbx+20h], 0
0x18003a0be  setz    sil
0x18003a0c2  mov     [rbp+var_17], dil
0x18003a0c6  xor     r14b, r14b
0x18003a0c9  mov     [rbp+var_18], sil
0x18003a0cd  lea     rax, ?CallOriginalWndProc@@YA_JPEAUHWND__@@I_K_J11@Z; CallOriginalWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x18003a0d4  mov     [rbx], edi
0x18003a0d6  xor     r15b, r15b
0x18003a0d9  mov     [rbx+18h], rax
0x18003a0dd  jmp     short loc_18003A11A
0x18003a0df  test    eax, eax
0x18003a0e1  mov     edx, r15d; nIndex
0x18003a0e4  mov     rcx, rdi; hWnd
0x18003a0e7  setnz   r14b
0x18003a0eb  mov     [rbp+arg_18], r14b
0x18003a0ef  call    cs:__imp_GetWindowLongPtrW
0x18003a0f5  mov     rdx, rbx; struct SUBCLASS_HEADER *
0x18003a0f8  mov     rcx, rdi; HWND
0x18003a0fb  test    rax, rax
0x18003a0fe  setz    [rbp+arg_10]
0x18003a102  cmp     rax, rsi
0x18003a105  setz    r15b
0x18003a109  mov     [rbp+arg_8], r15b
0x18003a10d  call    ?FreeSubclassHeader@@YAXPEAUHWND__@@PEAUSUBCLASS_HEADER@@@Z; FreeSubclassHeader(HWND__ *,SUBCLASS_HEADER *)
0x18003a112  xor     ebx, ebx
0x18003a114  xor     dil, dil
0x18003a117  xor     sil, sil
0x18003a11a  lea     rax, [rbp+arg_8]
0x18003a11e  mov     [rsp+58h+var_28], rax
0x18003a123  lea     r9, [rbp+arg_18]
0x18003a127  lea     rax, [rbp+arg_10]
0x18003a12b  mov     [rsp+58h+var_30], rax
0x18003a130  lea     r8, [rbp+var_18]
0x18003a134  lea     rax, [rbp+var_14]
0x18003a138  lea     rdx, [rbp+var_17]
0x18003a13c  mov     [rsp+58h+var_38], rax
0x18003a141  lea     rcx, [rbp+arg_0]
0x18003a145  call    ??$SHSetWindowSubclassAttach@AEAPEAUHWND__@@AEA_NAEA_NAEA_NAEAKAEA_NAEA_N@SHCoreTelemetry@@SAXAEAPEAUHWND__@@AEA_N11AEAK11@Z; SHCoreTelemetry::SHSetWindowSubclassAttach<HWND__ * &,bool &,bool &,bool &,ulong &,bool &,bool &>(HWND__ * &,bool &,bool &,bool &,ulong &,bool &,bool &)
0x18003a14a  test    dil, dil
0x18003a14d  jnz     short loc_18003A159
0x18003a14f  test    r14b, r14b
0x18003a152  jnz     short loc_18003A159
0x18003a154  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a159  test    sil, sil
0x18003a15c  jz      short loc_18003A163
0x18003a15e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a163  test    r15b, r15b
0x18003a166  jz      loc_18003A015
0x18003a16c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a171  jmp     loc_18003A015
```
