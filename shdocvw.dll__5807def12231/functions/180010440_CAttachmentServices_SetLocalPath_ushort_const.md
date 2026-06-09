# CAttachmentServices::SetLocalPath(ushort const *)

- ea: `0x180010440`
- end: `0x1800104b6`
- name: `?SetLocalPath@CAttachmentServices@@UEAAJPEBG@Z`
- size: `118`
- prototype: `__int64 __fastcall(CAttachmentServices *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004340`
- `0x18001003c`
- `0x180010440`
- `0x180011354`
- `0x1800114c4`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180010476`
- `SHLWAPI!PathFindFileNameW` at `0x180010476`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010491`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010491`

## pseudocode

```c
__int64 __fastcall CAttachmentServices::SetLocalPath(CAttachmentServices *this, const unsigned __int16 *a2)
{
  const WCHAR *FileNameW; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]

  CAttachmentServices::_SetProperty(this, (unsigned __int16 **)this + 5, a2, 0x104u, bIgnoreCase);
  if ( (unsigned int)CAttachmentServices::Continuable(this) )
  {
    if ( *((_QWORD *)this + 4) )
    {
      FileNameW = PathFindFileNameW(*((LPCWSTR *)this + 5));
      if ( CompareStringOrdinal(*((LPCWCH *)this + 4), -1, FileNameW, -1, 1) != 2 )
        CAttachmentServices::_ResetOps(this);
    }
  }
  return CAttachmentServices::Result(this);
}

```

## disassembly

```asm
0x180010440  mov     [rsp+arg_0], rbx
0x180010445  push    rdi
0x180010446  sub     rsp, 30h
0x18001044a  mov     r8, rdx; unsigned __int16 *
0x18001044d  mov     r9d, 104h; unsigned __int64
0x180010453  lea     rdx, [rcx+28h]; unsigned __int16 **
0x180010457  mov     rbx, rcx
0x18001045a  call    ?_SetProperty@CAttachmentServices@@AEAAXPEAPEAGPEBG_KK@Z; CAttachmentServices::_SetProperty(ushort * *,ushort const *,unsigned __int64,ulong)
0x18001045f  mov     rcx, rbx; this
0x180010462  call    ?Continuable@CAttachmentServices@@AEAAHXZ; CAttachmentServices::Continuable(void)
0x180010467  test    eax, eax
0x180010469  jz      short loc_1800104A4
0x18001046b  cmp     qword ptr [rbx+20h], 0
0x180010470  jz      short loc_1800104A4
0x180010472  mov     rcx, [rbx+28h]; pszPath
0x180010476  call    cs:__imp_PathFindFileNameW
0x18001047c  mov     rcx, [rbx+20h]; lpString1
0x180010480  or      edx, 0FFFFFFFFh; cchCount1
0x180010483  mov     r9d, edx; cchCount2
0x180010486  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18001048e  mov     r8, rax; lpString2
0x180010491  call    cs:__imp_CompareStringOrdinal
0x180010497  cmp     eax, 2
0x18001049a  jz      short loc_1800104A4
0x18001049c  mov     rcx, rbx; this
0x18001049f  call    ?_ResetOps@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_ResetOps(void)
0x1800104a4  mov     rcx, rbx; this
0x1800104a7  mov     rbx, [rsp+38h+arg_0]
0x1800104ac  add     rsp, 30h
0x1800104b0  pop     rdi
0x1800104b1  jmp     ?Result@CAttachmentServices@@AEAAJXZ; CAttachmentServices::Result(void)
```
