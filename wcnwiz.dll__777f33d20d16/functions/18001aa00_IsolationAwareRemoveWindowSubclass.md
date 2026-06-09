# IsolationAwareRemoveWindowSubclass

- ea: `0x18001aa00`
- end: `0x18001aad1`
- name: `IsolationAwareRemoveWindowSubclass`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a800`

## callees

- `0x18000d428`
- `0x180011874`
- `0x18001aa00`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001aab9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001aab9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe57`
- `KERNEL32!DeactivateActCtx` at `0x18001aaad`
- `KERNEL32!DeactivateActCtx` at `0x18002fe4b`
- `KERNEL32!DeactivateActCtx` at `0x18001aaad`
- `KERNEL32!DeactivateActCtx` at `0x18002fe4b`

## string_xrefs

- `0x18001aa49`: `RemoveWindowSubclass`

## pseudocode

```c
__int64 __fastcall IsolationAwareRemoveWindowSubclass(__int64 a1)
{
  unsigned int v2; // edi
  __int64 (__fastcall *v3)(__int64, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64), _QWORD); // rbx
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v3 = (__int64 (__fastcall *)(__int64, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64), _QWORD))`IsolationAwareRemoveWindowSubclass'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    result = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)result )
      return result;
  }
  if ( !v3 )
  {
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("RemoveWindowSubclass");
    v3 = (__int64 (__fastcall *)(__int64, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64), _QWORD))v5;
    if ( !v5 )
      goto LABEL_8;
    `IsolationAwareRemoveWindowSubclass'::`2'::s_pfn = v5;
  }
  v2 = v3(a1, CWcnTaskConnectToAp::WizardSubClassDlgProc, 0);
LABEL_8:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v6 = 0;
      LastError = 0;
    }
    else
    {
      v6 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v6 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x18001aa00  mov     rax, rsp
0x18001aa03  mov     [rax+8], rbx
0x18001aa07  mov     [rax+10h], rsi
0x18001aa0b  mov     [rax+18h], r8
0x18001aa0f  push    rdi
0x18001aa10  sub     rsp, 30h
0x18001aa14  mov     rsi, rcx
0x18001aa17  xor     edi, edi
0x18001aa19  mov     [rax-18h], edi
0x18001aa1c  mov     rbx, cs:?s_pfn@?1??IsolationAwareRemoveWindowSubclass@@9@4P6AHPEAUHWND__@@P6A_J0I_K_J11@Z1@ZEA; int (*`IsolationAwareRemoveWindowSubclass'::`2'::s_pfn)(HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64),unsigned __int64)
0x18001aa23  mov     [rax+18h], rdi
0x18001aa27  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x18001aa2d  jnz     short loc_18001AA44
0x18001aa2f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18001aa35  jnz     short loc_18001AA44
0x18001aa37  lea     rcx, [rax+18h]; lpCookie
0x18001aa3b  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001aa40  test    eax, eax
0x18001aa42  jz      short loc_18001AAC1
0x18001aa44  test    rbx, rbx
0x18001aa47  jnz     short loc_18001AA64
0x18001aa49  lea     rcx, aRemovewindowsu; "RemoveWindowSubclass"
0x18001aa50  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18001aa55  mov     rbx, rax
0x18001aa58  test    rax, rax
0x18001aa5b  jz      short loc_18001AA7F
0x18001aa5d  mov     cs:?s_pfn@?1??IsolationAwareRemoveWindowSubclass@@9@4P6AHPEAUHWND__@@P6A_J0I_K_J11@Z1@ZEA, rax; int (*`IsolationAwareRemoveWindowSubclass'::`2'::s_pfn)(HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64),unsigned __int64)
0x18001aa64  xor     r8d, r8d
0x18001aa67  lea     rdx, ?WizardSubClassDlgProc@CWcnTaskConnectToAp@@SA_JPEAUHWND__@@I_K_J11@Z; CWcnTaskConnectToAp::WizardSubClassDlgProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x18001aa6e  mov     rcx, rsi
0x18001aa71  mov     rax, rbx
0x18001aa74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa79  mov     edi, eax
0x18001aa7b  mov     [rsp+38h+var_18], eax
0x18001aa7f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001aa86  jz      short loc_18001AA91
0x18001aa88  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001aa8f  jnz     short loc_18001AABF
0x18001aa91  test    edi, edi
0x18001aa93  jnz     short loc_18001AAA2
0x18001aa95  lea     esi, [rdi+1]
0x18001aa98  call    cs:__imp_GetLastError
0x18001aa9e  mov     ebx, eax
0x18001aaa0  jmp     short loc_18001AAA6
0x18001aaa2  xor     esi, esi
0x18001aaa4  xor     ebx, ebx
0x18001aaa6  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18001aaab  xor     ecx, ecx; dwFlags
0x18001aaad  call    cs:__imp_DeactivateActCtx
0x18001aab3  test    esi, esi
0x18001aab5  jz      short loc_18001AABF
0x18001aab7  mov     ecx, ebx; dwErrCode
0x18001aab9  call    cs:__imp_SetLastError
0x18001aabf  mov     eax, edi
0x18001aac1  mov     rbx, [rsp+38h+arg_0]
0x18001aac6  mov     rsi, [rsp+38h+arg_8]
0x18001aacb  add     rsp, 30h
0x18001aacf  pop     rdi
0x18001aad0  retn
0x18002fe0f  push    rbx
0x18002fe11  push    rbp
0x18002fe12  push    rdi
0x18002fe13  sub     rsp, 20h
0x18002fe17  mov     rbp, rdx
0x18002fe1a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002fe21  jz      short loc_18002FE2C
0x18002fe23  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002fe2a  jnz     short loc_18002FE5E
0x18002fe2c  cmp     dword ptr [rbp+20h], 0
0x18002fe30  jnz     short loc_18002FE41
0x18002fe32  mov     edi, 1
0x18002fe37  call    cs:__imp_GetLastError
0x18002fe3d  mov     ebx, eax
0x18002fe3f  jmp     short loc_18002FE45
0x18002fe41  xor     edi, edi
0x18002fe43  xor     ebx, ebx
0x18002fe45  mov     rdx, [rbp+50h]; ulCookie
0x18002fe49  xor     ecx, ecx; dwFlags
0x18002fe4b  call    cs:__imp_DeactivateActCtx
0x18002fe51  test    edi, edi
0x18002fe53  jz      short loc_18002FE5E
0x18002fe55  mov     ecx, ebx; dwErrCode
0x18002fe57  call    cs:__imp_SetLastError
0x18002fe5d  nop
0x18002fe5e  add     rsp, 20h
0x18002fe62  pop     rdi
0x18002fe63  pop     rbp
0x18002fe64  pop     rbx
0x18002fe65  retn
```
