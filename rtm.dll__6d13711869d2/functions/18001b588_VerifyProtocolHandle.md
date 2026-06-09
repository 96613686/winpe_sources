# VerifyProtocolHandle

- ea: `0x18001b588`
- end: `0x18001b662`
- name: `VerifyProtocolHandle`
- size: `218`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011850`
- `0x180012620`
- `0x180012800`
- `0x180013930`
- `0x180014580`
- `0x180014970`

## callees

- `0x18001b588`
- `0x180020010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x18001b5f2`
- `rtutils!RouterLogEventA` at `0x18001b653`
- `rtutils!RouterLogEventA` at `0x18001b5f2`
- `rtutils!RouterLogEventA` at `0x18001b653`

## string_xrefs

- `0x18001b5ae`: `Invalid protocol handle`
- `0x18001b60f`: `Invalid protocol handle`

## pseudocode

```c
__int64 __fastcall VerifyProtocolHandle(__int64 a1)
{
  unsigned int v1; // ebx

  v1 = 0;
  if ( *(_DWORD *)(a1 + 112) != 1296518512 )
  {
    v1 = 87;
    if ( qword_18002B8A8 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        qword_18002B8A8,
        L"Invalid protocol handle");
    if ( dword_18002BA54 )
      RouterLogEventA(qword_18002BA58, 1u, 0xC363u, 0, 0, 0x57u);
  }
  return v1;
}

```

## disassembly

```asm
0x18001b588  push    rbx
0x18001b58a  sub     rsp, 40h
0x18001b58e  xor     ebx, ebx
0x18001b590  cmp     dword ptr [rcx+70h], 4D474D70h
0x18001b597  jz      short loc_18001B5F8
0x18001b599  mov     ebx, 57h ; 'W'
0x18001b59e  mov     [rsp+48h+var_18], ebx
0x18001b5a2  mov     rdx, cs:qword_18002B8A8
0x18001b5a9  test    rdx, rdx
0x18001b5ac  jz      short loc_18001B5C8
0x18001b5ae  lea     r8, aInvalidProtoco; "Invalid protocol handle"
0x18001b5b5  mov     rcx, cs:gMgmEtwContext
0x18001b5bc  mov     rax, cs:gMgmTemplateFunc
0x18001b5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5c8  mov     edx, 1; dwEventType
0x18001b5cd  cmp     cs:dword_18002BA54, edx
0x18001b5d3  jb      short loc_18001B5F8
0x18001b5d5  mov     [rsp+48h+dwErrorCode], ebx; dwErrorCode
0x18001b5d9  mov     [rsp+48h+plpszSubStringArray], 0; plpszSubStringArray
0x18001b5e2  xor     r9d, r9d; dwSubStringCount
0x18001b5e5  mov     r8d, 0C363h; dwMessageId
0x18001b5eb  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001b5f2  call    cs:__imp_RouterLogEventA
0x18001b5f8  jmp     short loc_18001B65A
0x18001b5fa  mov     ebx, 57h ; 'W'
0x18001b5ff  mov     [rsp+48h+var_18], ebx
0x18001b603  mov     rdx, cs:qword_18002B8A8
0x18001b60a  test    rdx, rdx
0x18001b60d  jz      short loc_18001B629
0x18001b60f  lea     r8, aInvalidProtoco; "Invalid protocol handle"
0x18001b616  mov     rcx, cs:gMgmEtwContext
0x18001b61d  mov     rax, cs:gMgmTemplateFunc
0x18001b624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b629  cmp     cs:dword_18002BA54, 1
0x18001b630  jb      short loc_18001B65A
0x18001b632  mov     [rsp+48h+dwErrorCode], ebx; dwErrorCode
0x18001b636  mov     [rsp+48h+plpszSubStringArray], 0; plpszSubStringArray
0x18001b63f  xor     r9d, r9d; dwSubStringCount
0x18001b642  lea     edx, [r9+1]; dwEventType
0x18001b646  mov     r8d, 0C363h; dwMessageId
0x18001b64c  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001b653  call    cs:__imp_RouterLogEventA
0x18001b659  nop
0x18001b65a  mov     eax, ebx
0x18001b65c  add     rsp, 40h
0x18001b660  pop     rbx
0x18001b661  retn
0x18001fd1e  push    rbp
0x18001fd20  sub     rsp, 30h
0x18001fd24  mov     rbp, rdx
0x18001fd27  mov     rax, [rcx]
0x18001fd2a  xor     ecx, ecx
0x18001fd2c  cmp     dword ptr [rax], 0C0000005h
0x18001fd32  setz    cl
0x18001fd35  mov     eax, ecx
0x18001fd37  add     rsp, 30h
0x18001fd3b  pop     rbp
0x18001fd3c  retn
```
