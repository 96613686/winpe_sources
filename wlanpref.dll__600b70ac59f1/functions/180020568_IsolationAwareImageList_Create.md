# IsolationAwareImageList_Create

- ea: `0x180020568`
- end: `0x180020644`
- name: `IsolationAwareImageList_Create`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020214`

## callees

- `0x18000c6ec`
- `0x1800204a0`
- `0x180020568`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e717`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020636`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e737`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020636`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e737`
- `KERNEL32!DeactivateActCtx` at `0x18002062a`
- `KERNEL32!DeactivateActCtx` at `0x18002e72b`
- `KERNEL32!DeactivateActCtx` at `0x18002062a`
- `KERNEL32!DeactivateActCtx` at `0x18002e72b`

## string_xrefs

- `0x1800205b9`: `ImageList_Create`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_Create(unsigned int a1, unsigned int a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(_QWORD, _QWORD, __int64); // rbx
  __int64 v7; // rax
  int v8; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+38h] [rbp-30h]

  v4 = 0;
  v11 = 0;
  v5 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64))`IsolationAwareImageList_Create'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( !v5 )
  {
    v7 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_Create");
    v5 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64))v7;
    if ( !v7 )
      goto LABEL_9;
    `IsolationAwareImageList_Create'::`2'::s_pfn = v7;
  }
  v4 = v5(a1, a2, 33);
  v11 = v4;
LABEL_9:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v4 )
    {
      v8 = 0;
      LastError = 0;
    }
    else
    {
      v8 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v8 )
      SetLastError(LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x180020568  push    rbx
0x18002056a  push    rsi
0x18002056b  push    rdi
0x18002056c  push    r14
0x18002056e  sub     rsp, 48h
0x180020572  mov     esi, edx
0x180020574  mov     r14d, ecx
0x180020577  xor     edi, edi
0x180020579  mov     [rsp+68h+var_30], rdi
0x18002057e  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x180020585  mov     [rsp+68h+ulCookie], rdi
0x18002058a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180020590  jnz     short loc_1800205B4
0x180020592  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180020598  jnz     short loc_1800205B4
0x18002059a  lea     rcx, [rsp+68h+ulCookie]; lpCookie
0x18002059f  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800205a4  test    eax, eax
0x1800205a6  jnz     short loc_1800205B4
0x1800205a8  xor     eax, eax
0x1800205aa  add     rsp, 48h
0x1800205ae  pop     r14
0x1800205b0  pop     rdi
0x1800205b1  pop     rsi
0x1800205b2  pop     rbx
0x1800205b3  retn
0x1800205b4  test    rbx, rbx
0x1800205b7  jnz     short loc_1800205D4
0x1800205b9  lea     rcx, aImagelistCreat; "ImageList_Create"
0x1800205c0  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x1800205c5  mov     rbx, rax
0x1800205c8  test    rax, rax
0x1800205cb  jz      short loc_1800205FB
0x1800205cd  mov     cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA, rax; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x1800205d4  mov     [rsp+68h+var_48], 0
0x1800205dc  mov     r9d, 6
0x1800205e2  lea     r8d, [r9+1Bh]
0x1800205e6  mov     edx, esi
0x1800205e8  mov     ecx, r14d
0x1800205eb  mov     rax, rbx
0x1800205ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205f3  mov     rdi, rax
0x1800205f6  mov     [rsp+68h+var_30], rax
0x1800205fb  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180020602  jz      short loc_18002060D
0x180020604  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002060b  jnz     short loc_18002063C
0x18002060d  test    rdi, rdi
0x180020610  jnz     short loc_18002061F
0x180020612  lea     esi, [rdi+1]
0x180020615  call    cs:__imp_GetLastError
0x18002061b  mov     ebx, eax
0x18002061d  jmp     short loc_180020623
0x18002061f  xor     esi, esi
0x180020621  xor     ebx, ebx
0x180020623  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x180020628  xor     ecx, ecx; dwFlags
0x18002062a  call    cs:__imp_DeactivateActCtx
0x180020630  test    esi, esi
0x180020632  jz      short loc_18002063C
0x180020634  mov     ecx, ebx; dwErrCode
0x180020636  call    cs:__imp_SetLastError
0x18002063c  mov     rax, rdi
0x18002063f  jmp     loc_1800205AA
0x18002e6ee  push    rbx
0x18002e6f0  push    rbp
0x18002e6f1  push    rdi
0x18002e6f2  sub     rsp, 30h
0x18002e6f6  mov     rbp, rdx
0x18002e6f9  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002e700  jz      short loc_18002E70B
0x18002e702  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002e709  jnz     short loc_18002E73E
0x18002e70b  cmp     qword ptr [rbp+38h], 0
0x18002e710  jnz     short loc_18002E721
0x18002e712  mov     edi, 1
0x18002e717  call    cs:__imp_GetLastError
0x18002e71d  mov     ebx, eax
0x18002e71f  jmp     short loc_18002E725
0x18002e721  xor     edi, edi
0x18002e723  xor     ebx, ebx
0x18002e725  mov     rdx, [rbp+30h]; ulCookie
0x18002e729  xor     ecx, ecx; dwFlags
0x18002e72b  call    cs:__imp_DeactivateActCtx
0x18002e731  test    edi, edi
0x18002e733  jz      short loc_18002E73E
0x18002e735  mov     ecx, ebx; dwErrCode
0x18002e737  call    cs:__imp_SetLastError
0x18002e73d  nop
0x18002e73e  add     rsp, 30h
0x18002e742  pop     rdi
0x18002e743  pop     rbp
0x18002e744  pop     rbx
0x18002e745  retn
```
