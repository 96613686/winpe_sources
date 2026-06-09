# mslib::EventLogger<UwfEtwProvider>::Log(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ulong)

- ea: `0x18000266c`
- end: `0x1800027bf`
- name: `?Log@?$EventLogger@VUwfEtwProvider@@@mslib@@QEBAKAEBU_EVENT_DESCRIPTOR@@PEBG1K@Z`
- size: `339`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, ULONGLONG, __int64, DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a20`

## callees

- `0x18000266c`
- `0x180005175`
- `0x1800051a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180002796`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180002796`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002738`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002738`

## pseudocode

```c
ULONG __fastcall mslib::EventLogger<UwfEtwProvider>::Log(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        ULONGLONG a3,
        __int64 a4,
        DWORD dwMessageId)
{
  __int64 v6; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+58h] [rbp-A8h]
  int v14; // [rsp+5Ch] [rbp-A4h]
  DWORD *p_dwMessageId; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+68h] [rbp-98h]
  WCHAR *v17; // [rsp+70h] [rbp-90h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  WCHAR Buffer[512]; // [rsp+80h] [rbp-80h] BYREF

  UserData.Ptr = a3;
  v6 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a3 + 2 * v8) );
  UserData.Reserved = 0;
  UserData.Size = 2 * v8 + 2;
  v12 = a4;
  do
    ++v6;
  while ( *(_WORD *)(a4 + 2 * v6) );
  v14 = 0;
  v13 = 2 * v6 + 2;
  v16 = 4;
  p_dwMessageId = &dwMessageId;
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !dwMessageId )
    goto LABEL_10;
  LODWORD(v9) = FormatMessageW(0x1200u, 0, dwMessageId, 0x400u, Buffer, 0x1FFu, 0);
  if ( (unsigned int)v9 >= 0x1FF )
    v9 = 510;
  Buffer[v9] = 0;
  if ( (_DWORD)v9 )
  {
    v17 = Buffer;
    v18 = (unsigned int)(2 * v9 + 2);
  }
  else
  {
LABEL_10:
    v18 = 2;
    v17 = (WCHAR *)&dword_180008E4C;
  }
  return EventWrite(*a1, a2, 4u, &UserData);
}

```

## disassembly

```asm
0x18000266c  mov     [rsp-8+arg_10], rbx
0x180002671  push    rbp
0x180002672  push    rdi
0x180002673  push    r14
0x180002675  lea     rbp, [rsp-390h]
0x18000267d  sub     rsp, 490h
0x180002684  mov     rax, cs:__security_cookie
0x18000268b  xor     rax, rsp
0x18000268e  mov     [rbp+3A0h+var_20], rax
0x180002695  mov     rdi, rdx
0x180002698  mov     [rsp+4A0h+UserData.Ptr], r8
0x18000269d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800026a1  mov     rbx, rcx
0x1800026a4  mov     rax, rdx
0x1800026a7  xor     r14d, r14d
0x1800026aa  inc     rax
0x1800026ad  cmp     [r8+rax*2], r14w
0x1800026b2  jnz     short loc_1800026AA
0x1800026b4  lea     eax, ds:2[rax*2]
0x1800026bb  mov     dword ptr [rsp+4A0h+UserData.0Ch], r14d
0x1800026c0  mov     [rsp+4A0h+UserData.Size], eax
0x1800026c4  mov     [rsp+4A0h+var_450], r9
0x1800026c9  inc     rdx
0x1800026cc  cmp     [r9+rdx*2], r14w
0x1800026d1  jnz     short loc_1800026C9
0x1800026d3  lea     eax, ds:2[rdx*2]
0x1800026da  mov     [rsp+4A0h+var_444], r14d
0x1800026df  mov     [rsp+4A0h+var_448], eax
0x1800026e3  lea     rcx, [rbp+3A0h+Buffer]; void *
0x1800026e7  lea     rax, [rbp+3A0h+dwMessageId]
0x1800026ee  mov     [rsp+4A0h+var_438], 4
0x1800026f7  xor     edx, edx; Val
0x1800026f9  mov     [rsp+4A0h+var_440], rax
0x1800026fe  mov     r8d, 400h; Size
0x180002704  call    memset_0
0x180002709  mov     r8d, [rbp+3A0h+dwMessageId]; dwMessageId
0x180002710  test    r8d, r8d
0x180002713  jz      short loc_180002770
0x180002715  mov     [rsp+4A0h+Arguments], r14; Arguments
0x18000271a  lea     rax, [rbp+3A0h+Buffer]
0x18000271e  mov     [rsp+4A0h+nSize], 1FFh; nSize
0x180002726  xor     edx, edx; lpSource
0x180002728  mov     ecx, 1200h; dwFlags
0x18000272d  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x180002732  mov     r9d, 400h; dwLanguageId
0x180002738  call    cs:__imp_FormatMessageW
0x18000273e  cmp     eax, 1FFh
0x180002743  mov     ecx, 1FEh
0x180002748  cmovnb  eax, ecx
0x18000274b  mov     [rbp+rax*2+3A0h+Buffer], r14w
0x180002751  test    eax, eax
0x180002753  jz      short loc_180002770
0x180002755  lea     rcx, [rbp+3A0h+Buffer]
0x180002759  mov     dword ptr [rsp+4A0h+var_428+4], r14d
0x18000275e  lea     eax, ds:2[rax*2]
0x180002765  mov     [rsp+4A0h+var_430], rcx
0x18000276a  mov     dword ptr [rsp+4A0h+var_428], eax
0x18000276e  jmp     short loc_180002785
0x180002770  lea     rax, dword_180008E4C
0x180002777  mov     [rsp+4A0h+var_428], 2
0x180002780  mov     [rsp+4A0h+var_430], rax
0x180002785  mov     rcx, [rbx]; RegHandle
0x180002788  lea     r9, [rsp+4A0h+UserData]; UserData
0x18000278d  mov     r8d, 4; UserDataCount
0x180002793  mov     rdx, rdi; EventDescriptor
0x180002796  call    cs:__imp_EventWrite
0x18000279c  mov     rcx, [rbp+3A0h+var_20]
0x1800027a3  xor     rcx, rsp; StackCookie
0x1800027a6  call    __security_check_cookie
0x1800027ab  mov     rbx, [rsp+4A0h+arg_10]
0x1800027b3  add     rsp, 490h
0x1800027ba  pop     r14
0x1800027bc  pop     rdi
0x1800027bd  pop     rbp
0x1800027be  retn
```
