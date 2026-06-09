# IsolationAwareImageList_Create

- ea: `0x180011920`
- end: `0x180011a0b`
- name: `IsolationAwareImageList_Create`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010ab0`
- `0x18001c010`

## callees

- `0x18000d428`
- `0x180011874`
- `0x180011920`
- `0x18001a918`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800119fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800119fd`
- `KERNEL32!DeactivateActCtx` at `0x1800119f1`
- `KERNEL32!DeactivateActCtx` at `0x1800119f1`

## string_xrefs

- `0x180011980`: `ImageList_Create`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_Create(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(_QWORD, _QWORD, _QWORD, _QWORD, int); // rbx
  __int64 v12; // rax
  int v13; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h]

  v9 = 0;
  v16 = 0;
  v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, int))`IsolationAwareImageList_Create'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( !v10 )
  {
    v12 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_Create");
    v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, int))v12;
    if ( !v12 )
      goto LABEL_9;
    `IsolationAwareImageList_Create'::`2'::s_pfn = v12;
  }
  v9 = v10(a1, a2, a3, a4, a5);
  v16 = v9;
LABEL_9:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v9 )
    {
      v13 = 0;
      LastError = 0;
    }
    else
    {
      v13 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v13 )
      SetLastError(LastError);
  }
  return v9;
}

```

## disassembly

```asm
0x180011920  push    rbx
0x180011922  push    rsi
0x180011923  push    rdi
0x180011924  push    r12
0x180011926  push    r14
0x180011928  push    r15
0x18001192a  sub     rsp, 48h
0x18001192e  mov     esi, r9d
0x180011931  mov     r14d, r8d
0x180011934  mov     r15d, edx
0x180011937  mov     r12d, ecx
0x18001193a  xor     edi, edi
0x18001193c  mov     [rsp+78h+var_40], rdi
0x180011941  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x180011948  mov     [rsp+78h+ulCookie], rdi
0x18001194d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180011953  jnz     short loc_18001197B
0x180011955  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18001195b  jnz     short loc_18001197B
0x18001195d  lea     rcx, [rsp+78h+ulCookie]; lpCookie
0x180011962  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180011967  test    eax, eax
0x180011969  jnz     short loc_18001197B
0x18001196b  xor     eax, eax
0x18001196d  add     rsp, 48h
0x180011971  pop     r15
0x180011973  pop     r14
0x180011975  pop     r12
0x180011977  pop     rdi
0x180011978  pop     rsi
0x180011979  pop     rbx
0x18001197a  retn
0x18001197b  test    rbx, rbx
0x18001197e  jnz     short loc_18001199B
0x180011980  lea     rcx, aImagelistCreat; "ImageList_Create"
0x180011987  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18001198c  mov     rbx, rax
0x18001198f  test    rax, rax
0x180011992  jz      short loc_1800119C2
0x180011994  mov     cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA, rax; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x18001199b  mov     eax, [rsp+78h+arg_20]
0x1800119a2  mov     [rsp+78h+var_58], eax
0x1800119a6  mov     r9d, esi
0x1800119a9  mov     r8d, r14d
0x1800119ac  mov     edx, r15d
0x1800119af  mov     ecx, r12d
0x1800119b2  mov     rax, rbx
0x1800119b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119ba  mov     rdi, rax
0x1800119bd  mov     [rsp+78h+var_40], rax
0x1800119c2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800119c9  jz      short loc_1800119D4
0x1800119cb  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800119d2  jnz     short loc_180011A03
0x1800119d4  test    rdi, rdi
0x1800119d7  jnz     short loc_1800119E6
0x1800119d9  lea     esi, [rdi+1]
0x1800119dc  call    cs:__imp_GetLastError
0x1800119e2  mov     ebx, eax
0x1800119e4  jmp     short loc_1800119EA
0x1800119e6  xor     esi, esi
0x1800119e8  xor     ebx, ebx
0x1800119ea  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x1800119ef  xor     ecx, ecx; dwFlags
0x1800119f1  call    cs:__imp_DeactivateActCtx
0x1800119f7  test    esi, esi
0x1800119f9  jz      short loc_180011A03
0x1800119fb  mov     ecx, ebx; dwErrCode
0x1800119fd  call    cs:__imp_SetLastError
0x180011a03  mov     rax, rdi
0x180011a06  jmp     loc_18001196D
0x18002fb36  push    rbx
0x18002fb38  push    rbp
0x18002fb39  push    rdi
0x18002fb3a  sub     rsp, 30h
0x18002fb3e  mov     rbp, rdx
0x18002fb41  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002fb48  jz      short loc_18002FB53
0x18002fb4a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002fb51  jnz     short loc_18002FB86
0x18002fb53  cmp     qword ptr [rbp+38h], 0
0x18002fb58  jnz     short loc_18002FB69
0x18002fb5a  mov     edi, 1
0x18002fb5f  call    cs:__imp_GetLastError
0x18002fb65  mov     ebx, eax
0x18002fb67  jmp     short loc_18002FB6D
0x18002fb69  xor     edi, edi
0x18002fb6b  xor     ebx, ebx
0x18002fb6d  mov     rdx, [rbp+30h]; ulCookie
0x18002fb71  xor     ecx, ecx; dwFlags
0x18002fb73  call    cs:__imp_DeactivateActCtx
0x18002fb79  test    edi, edi
0x18002fb7b  jz      short loc_18002FB86
0x18002fb7d  mov     ecx, ebx; dwErrCode
0x18002fb7f  call    cs:__imp_SetLastError
0x18002fb85  nop
0x18002fb86  add     rsp, 30h
0x18002fb8a  pop     rdi
0x18002fb8b  pop     rbp
0x18002fb8c  pop     rbx
0x18002fb8d  retn
```
