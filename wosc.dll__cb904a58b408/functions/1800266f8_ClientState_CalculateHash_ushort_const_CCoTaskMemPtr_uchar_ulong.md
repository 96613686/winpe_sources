# ClientState::CalculateHash(ushort const *,CCoTaskMemPtr<uchar> &,ulong *)

- ea: `0x1800266f8`
- end: `0x1800267b6`
- name: `?CalculateHash@ClientState@@CAJPEBGAEAV?$CCoTaskMemPtr@E@@PEAK@Z`
- size: `190`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002afa8`
- `0x18002b074`
- `0x18002b1a0`

## callees

- `0x180009e38`
- `0x1800101fc`
- `0x180019ed8`
- `0x1800266f8`
- `0x180028508`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026787`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026787`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026718`

## string_xrefs

- `0x180026732`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002676a`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClientState::CalculateHash(unsigned __int16 *a1, void **a2, _DWORD *a3)
{
  void *v6; // rax
  const char *v7; // r9
  void *v8; // rbx
  __int64 v9; // rdx
  int Sha256Hash; // eax
  unsigned int v11; // esi
  void *v12; // rcx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *v16; // [rsp+58h] [rbp+20h] BYREF

  v6 = CoTaskMemAlloc(0x20u);
  v8 = v6;
  v16 = v6;
  if ( !v6 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x522,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      v7);
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  Sha256Hash = EncryptionHelper::GetSha256Hash(a1, v9, (unsigned __int8 *)v6, (unsigned int)v7);
  v11 = Sha256Hash;
  if ( Sha256Hash < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x525,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)Sha256Hash,
      v14);
  v16 = 0;
  v12 = *a2;
  *a2 = 0;
  CoTaskMemFree(v12);
  *a2 = v8;
  *a3 = 32;
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v16);
  return v11;
}

```

## disassembly

```asm
0x1800266f8  mov     [rsp+arg_0], rbx
0x1800266fd  mov     [rsp+arg_8], rbp
0x180026702  push    rsi
0x180026703  push    rdi
0x180026704  push    r14; int
0x180026706  sub     rsp, 20h
0x18002670a  mov     r14, r8
0x18002670d  mov     rdi, rdx
0x180026710  mov     rsi, rcx
0x180026713  mov     ecx, 20h ; ' '; cb
0x180026718  call    cs:__imp_CoTaskMemAlloc
0x18002671e  mov     rbx, rax
0x180026721  mov     [rsp+38h+arg_18], rax
0x180026726  mov     rcx, [rsp+38h]; this
0x18002672b  xor     ebp, ebp
0x18002672d  test    rax, rax
0x180026730  jnz     short loc_180026744
0x180026732  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180026739  mov     edx, 522h; void *
0x18002673e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180026744  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180026748  inc     rdx; unsigned int
0x18002674b  cmp     [rsi+rdx*2], bp
0x18002674f  jnz     short loc_180026748
0x180026751  mov     r8, rbx; unsigned __int8 *
0x180026754  mov     rcx, rsi; unsigned __int16 *
0x180026757  call    ?GetSha256Hash@EncryptionHelper@@SAJPEBGKPEAEK@Z; EncryptionHelper::GetSha256Hash(ushort const *,ulong,uchar *,ulong)
0x18002675c  mov     esi, eax
0x18002675e  mov     rcx, [rsp+38h]; this
0x180026763  test    eax, eax
0x180026765  jns     short loc_18002677C
0x180026767  mov     r9d, eax; char *
0x18002676a  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180026771  mov     edx, 525h; void *
0x180026776  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002677c  mov     [rsp+38h+arg_18], rbp
0x180026781  mov     rcx, [rdi]; pv
0x180026784  mov     [rdi], rbp
0x180026787  call    cs:__imp_CoTaskMemFree
0x18002678d  mov     [rdi], rbx
0x180026790  mov     dword ptr [r14], 20h ; ' '
0x180026797  lea     rcx, [rsp+38h+arg_18]
0x18002679c  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800267a1  mov     eax, esi
0x1800267a3  mov     rbx, [rsp+38h+arg_0]
0x1800267a8  mov     rbp, [rsp+38h+arg_8]
0x1800267ad  add     rsp, 20h
0x1800267b1  pop     r14
0x1800267b3  pop     rdi
0x1800267b4  pop     rsi
0x1800267b5  retn
```
