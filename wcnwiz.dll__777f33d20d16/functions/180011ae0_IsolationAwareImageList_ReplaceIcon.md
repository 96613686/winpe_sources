# IsolationAwareImageList_ReplaceIcon

- ea: `0x180011ae0`
- end: `0x180011bb2`
- name: `IsolationAwareImageList_ReplaceIcon`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010ab0`

## callees

- `0x18000d428`
- `0x180011874`
- `0x180011ae0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011ba5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fc3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011ba5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fc3b`
- `KERNEL32!DeactivateActCtx` at `0x180011b99`
- `KERNEL32!DeactivateActCtx` at `0x18002fc2f`
- `KERNEL32!DeactivateActCtx` at `0x180011b99`
- `KERNEL32!DeactivateActCtx` at `0x18002fc2f`

## string_xrefs

- `0x180011b38`: `ImageList_ReplaceIcon`

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
0x180011ae0  push    rbx
0x180011ae2  push    rsi
0x180011ae3  push    rdi
0x180011ae4  push    r14
0x180011ae6  sub     rsp, 38h
0x180011aea  mov     rsi, r8
0x180011aed  mov     r14, rcx
0x180011af0  or      edi, 0FFFFFFFFh
0x180011af3  mov     [rsp+58h+var_38], edi
0x180011af7  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_ReplaceIcon@@9@4P6AHPEAU_IMAGELIST@@HPEAUHICON__@@@ZEA; int (*`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn)(_IMAGELIST *,int,HICON__ *)
0x180011afe  mov     [rsp+58h+ulCookie], 0
0x180011b07  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180011b0e  jnz     short loc_180011B33
0x180011b10  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180011b17  jnz     short loc_180011B33
0x180011b19  lea     rcx, [rsp+58h+ulCookie]; lpCookie
0x180011b1e  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180011b23  test    eax, eax
0x180011b25  jnz     short loc_180011B33
0x180011b27  or      eax, edi
0x180011b29  add     rsp, 38h
0x180011b2d  pop     r14
0x180011b2f  pop     rdi
0x180011b30  pop     rsi
0x180011b31  pop     rbx
0x180011b32  retn
0x180011b33  test    rbx, rbx
0x180011b36  jnz     short loc_180011B53
0x180011b38  lea     rcx, aImagelistRepla; "ImageList_ReplaceIcon"
0x180011b3f  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180011b44  mov     rbx, rax
0x180011b47  test    rax, rax
0x180011b4a  jz      short loc_180011B6A
0x180011b4c  mov     cs:?s_pfn@?1??IsolationAwareImageList_ReplaceIcon@@9@4P6AHPEAU_IMAGELIST@@HPEAUHICON__@@@ZEA, rax; int (*`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn)(_IMAGELIST *,int,HICON__ *)
0x180011b53  mov     r8, rsi
0x180011b56  or      edx, 0FFFFFFFFh
0x180011b59  mov     rcx, r14
0x180011b5c  mov     rax, rbx
0x180011b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b64  mov     edi, eax
0x180011b66  mov     [rsp+58h+var_38], eax
0x180011b6a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180011b71  jz      short loc_180011B7C
0x180011b73  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180011b7a  jnz     short loc_180011BAB
0x180011b7c  cmp     edi, 0FFFFFFFFh
0x180011b7f  jnz     short loc_180011B8E
0x180011b81  lea     esi, [rdi+2]
0x180011b84  call    cs:__imp_GetLastError
0x180011b8a  mov     ebx, eax
0x180011b8c  jmp     short loc_180011B92
0x180011b8e  xor     esi, esi
0x180011b90  xor     ebx, ebx
0x180011b92  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x180011b97  xor     ecx, ecx; dwFlags
0x180011b99  call    cs:__imp_DeactivateActCtx
0x180011b9f  test    esi, esi
0x180011ba1  jz      short loc_180011BAB
0x180011ba3  mov     ecx, ebx; dwErrCode
0x180011ba5  call    cs:__imp_SetLastError
0x180011bab  mov     eax, edi
0x180011bad  jmp     loc_180011B29
0x18002fbf3  push    rbx
0x18002fbf5  push    rbp
0x18002fbf6  push    rdi
0x18002fbf7  sub     rsp, 20h
0x18002fbfb  mov     rbp, rdx
0x18002fbfe  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002fc05  jz      short loc_18002FC10
0x18002fc07  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002fc0e  jnz     short loc_18002FC42
0x18002fc10  cmp     dword ptr [rbp+20h], 0FFFFFFFFh
0x18002fc14  jnz     short loc_18002FC25
0x18002fc16  mov     edi, 1
0x18002fc1b  call    cs:__imp_GetLastError
0x18002fc21  mov     ebx, eax
0x18002fc23  jmp     short loc_18002FC29
0x18002fc25  xor     edi, edi
0x18002fc27  xor     ebx, ebx
0x18002fc29  mov     rdx, [rbp+78h]; ulCookie
0x18002fc2d  xor     ecx, ecx; dwFlags
0x18002fc2f  call    cs:__imp_DeactivateActCtx
0x18002fc35  test    edi, edi
0x18002fc37  jz      short loc_18002FC42
0x18002fc39  mov     ecx, ebx; dwErrCode
0x18002fc3b  call    cs:__imp_SetLastError
0x18002fc41  nop
0x18002fc42  add     rsp, 20h
0x18002fc46  pop     rdi
0x18002fc47  pop     rbp
0x18002fc48  pop     rbx
0x18002fc49  retn
```
