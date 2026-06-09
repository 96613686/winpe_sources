# IsolationAwareImageList_ReplaceIcon

- ea: `0x180020718`
- end: `0x1800207ea`
- name: `IsolationAwareImageList_ReplaceIcon`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020214`

## callees

- `0x18000c6ec`
- `0x1800204a0`
- `0x180020718`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e7d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e7d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800207dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e7f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800207dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e7f3`
- `KERNEL32!DeactivateActCtx` at `0x1800207d1`
- `KERNEL32!DeactivateActCtx` at `0x18002e7e7`
- `KERNEL32!DeactivateActCtx` at `0x1800207d1`
- `KERNEL32!DeactivateActCtx` at `0x18002e7e7`

## string_xrefs

- `0x180020770`: `ImageList_ReplaceIcon`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_ReplaceIcon(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  __int64 (__fastcall *v6)(__int64, __int64, __int64); // rbx
  __int64 v8; // rax
  int v9; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+78h] [rbp+20h] BYREF

  v5 = -1;
  v6 = (__int64 (__fastcall *)(__int64, __int64, __int64))`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0xFFFFFFFFLL;
  }
  if ( !v6 )
  {
    v8 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_ReplaceIcon");
    v6 = (__int64 (__fastcall *)(__int64, __int64, __int64))v8;
    if ( !v8 )
      goto LABEL_9;
    `IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn = v8;
  }
  v5 = v6(a1, 0xFFFFFFFFLL, a3);
LABEL_9:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v5 == -1 )
    {
      v9 = 1;
      LastError = GetLastError();
    }
    else
    {
      v9 = 0;
      LastError = 0;
    }
    DeactivateActCtx(0, ulCookie);
    if ( v9 )
      SetLastError(LastError);
  }
  return v5;
}

```

## disassembly

```asm
0x180020718  push    rbx
0x18002071a  push    rsi
0x18002071b  push    rdi
0x18002071c  push    r14
0x18002071e  sub     rsp, 38h
0x180020722  mov     rsi, r8
0x180020725  mov     r14, rcx
0x180020728  or      edi, 0FFFFFFFFh
0x18002072b  mov     [rsp+58h+var_38], edi
0x18002072f  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_ReplaceIcon@@9@4P6AHPEAU_IMAGELIST@@HPEAUHICON__@@@ZEA; int (*`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn)(_IMAGELIST *,int,HICON__ *)
0x180020736  mov     [rsp+58h+ulCookie], 0
0x18002073f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180020746  jnz     short loc_18002076B
0x180020748  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002074f  jnz     short loc_18002076B
0x180020751  lea     rcx, [rsp+58h+ulCookie]; lpCookie
0x180020756  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18002075b  test    eax, eax
0x18002075d  jnz     short loc_18002076B
0x18002075f  or      eax, edi
0x180020761  add     rsp, 38h
0x180020765  pop     r14
0x180020767  pop     rdi
0x180020768  pop     rsi
0x180020769  pop     rbx
0x18002076a  retn
0x18002076b  test    rbx, rbx
0x18002076e  jnz     short loc_18002078B
0x180020770  lea     rcx, aImagelistRepla; "ImageList_ReplaceIcon"
0x180020777  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18002077c  mov     rbx, rax
0x18002077f  test    rax, rax
0x180020782  jz      short loc_1800207A2
0x180020784  mov     cs:?s_pfn@?1??IsolationAwareImageList_ReplaceIcon@@9@4P6AHPEAU_IMAGELIST@@HPEAUHICON__@@@ZEA, rax; int (*`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn)(_IMAGELIST *,int,HICON__ *)
0x18002078b  mov     r8, rsi
0x18002078e  or      edx, 0FFFFFFFFh
0x180020791  mov     rcx, r14
0x180020794  mov     rax, rbx
0x180020797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002079c  mov     edi, eax
0x18002079e  mov     [rsp+58h+var_38], eax
0x1800207a2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800207a9  jz      short loc_1800207B4
0x1800207ab  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800207b2  jnz     short loc_1800207E3
0x1800207b4  cmp     edi, 0FFFFFFFFh
0x1800207b7  jnz     short loc_1800207C6
0x1800207b9  lea     esi, [rdi+2]
0x1800207bc  call    cs:__imp_GetLastError
0x1800207c2  mov     ebx, eax
0x1800207c4  jmp     short loc_1800207CA
0x1800207c6  xor     esi, esi
0x1800207c8  xor     ebx, ebx
0x1800207ca  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x1800207cf  xor     ecx, ecx; dwFlags
0x1800207d1  call    cs:__imp_DeactivateActCtx
0x1800207d7  test    esi, esi
0x1800207d9  jz      short loc_1800207E3
0x1800207db  mov     ecx, ebx; dwErrCode
0x1800207dd  call    cs:__imp_SetLastError
0x1800207e3  mov     eax, edi
0x1800207e5  jmp     loc_180020761
0x18002e7ab  push    rbx
0x18002e7ad  push    rbp
0x18002e7ae  push    rdi
0x18002e7af  sub     rsp, 20h
0x18002e7b3  mov     rbp, rdx
0x18002e7b6  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002e7bd  jz      short loc_18002E7C8
0x18002e7bf  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002e7c6  jnz     short loc_18002E7FA
0x18002e7c8  cmp     dword ptr [rbp+20h], 0FFFFFFFFh
0x18002e7cc  jnz     short loc_18002E7DD
0x18002e7ce  mov     edi, 1
0x18002e7d3  call    cs:__imp_GetLastError
0x18002e7d9  mov     ebx, eax
0x18002e7db  jmp     short loc_18002E7E1
0x18002e7dd  xor     edi, edi
0x18002e7df  xor     ebx, ebx
0x18002e7e1  mov     rdx, [rbp+78h]; ulCookie
0x18002e7e5  xor     ecx, ecx; dwFlags
0x18002e7e7  call    cs:__imp_DeactivateActCtx
0x18002e7ed  test    edi, edi
0x18002e7ef  jz      short loc_18002E7FA
0x18002e7f1  mov     ecx, ebx; dwErrCode
0x18002e7f3  call    cs:__imp_SetLastError
0x18002e7f9  nop
0x18002e7fa  add     rsp, 20h
0x18002e7fe  pop     rdi
0x18002e7ff  pop     rbp
0x18002e800  pop     rbx
0x18002e801  retn
```
