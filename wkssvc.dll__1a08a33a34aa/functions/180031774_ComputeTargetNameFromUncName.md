# ComputeTargetNameFromUncName

- ea: `0x180031774`
- end: `0x18003186f`
- name: `ComputeTargetNameFromUncName`
- size: `251`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002be90`
- `0x180031968`
- `0x1800319cc`
- `0x180031de4`

## callees

- `0x18000eb1c`
- `0x180031774`
- `0x180036191`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18003183b`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18003183b`
- `ntdll!RtlInitUnicodeString` at `0x1800317f1`
- `ntdll!RtlInitUnicodeString` at `0x1800317f1`
- `ntdll!RtlHashUnicodeString` at `0x180031810`
- `ntdll!RtlHashUnicodeString` at `0x180031810`

## pseudocode

```c
__int64 __fastcall ComputeTargetNameFromUncName(_WORD *a1, char *a2)
{
  bool v3; // zf
  const WCHAR *v4; // rsi
  int v5; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  ULONG HashValue; // [rsp+60h] [rbp+8h] BYREF

  v3 = *a1 == 92;
  DestinationString = 0;
  HashValue = 0;
  if ( !v3 )
    return 0;
  if ( a1[1] != 92 )
    return 0;
  v4 = a1 + 2;
  if ( !a1[2] )
    return 0;
  v5 = 0;
  do
  {
    if ( v4[v5] == 92 )
      break;
    ++v5;
  }
  while ( v4[v5] );
  if ( v5 > 255 )
    return 0;
  memcpy_0(a2, a1 + 2, 2LL * v5);
  RtlInitUnicodeString(&DestinationString, v4);
  RtlHashUnicodeString(&DestinationString, 1u, 1u, &HashValue);
  *(_WORD *)&a2[2 * v5] = 95;
  _o__itow_s(HashValue, &a2[2 * v5 + 2], 9);
  StringCchCatW((STRSAFE_LPWSTR)a2, 0x151u, L".SMB-GlobalMapping-Target");
  return 1;
}

```

## disassembly

```asm
0x180031774  push    rbx
0x180031776  push    rsi
0x180031777  push    rdi
0x180031778  push    r14
0x18003177a  sub     rsp, 38h
0x18003177e  mov     r14, rdx
0x180031781  xorps   xmm0, xmm0
0x180031784  xor     edx, edx
0x180031786  cmp     word ptr [rcx], 5Ch ; '\'
0x18003178a  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18003178f  mov     [rsp+58h+HashValue], edx
0x180031793  jnz     loc_180031862
0x180031799  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18003179e  jnz     loc_180031862
0x1800317a4  lea     rsi, [rcx+4]
0x1800317a8  cmp     [rsi], dx
0x1800317ab  jz      loc_180031862
0x1800317b1  mov     edi, edx
0x1800317b3  movsxd  rax, edi
0x1800317b6  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x1800317bb  jz      short loc_1800317C8
0x1800317bd  inc     edi
0x1800317bf  movsxd  rax, edi
0x1800317c2  cmp     [rsi+rax*2], dx
0x1800317c6  jnz     short loc_1800317B3
0x1800317c8  cmp     edi, 0FFh
0x1800317ce  jg      loc_180031862
0x1800317d4  movsxd  rax, edi
0x1800317d7  mov     rdx, rsi; Src
0x1800317da  mov     rcx, r14; void *
0x1800317dd  lea     rbx, [rax+rax]
0x1800317e1  mov     r8, rbx; Size
0x1800317e4  call    memcpy_0
0x1800317e9  mov     rdx, rsi; SourceString
0x1800317ec  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1800317f1  call    cs:__imp_RtlInitUnicodeString
0x1800317f8  nop     dword ptr [rax+rax+00h]
0x1800317fd  mov     r8d, 1; HashAlgorithm
0x180031803  lea     r9, [rsp+58h+HashValue]; HashValue
0x180031808  mov     dl, r8b; CaseInSensitive
0x18003180b  lea     rcx, [rsp+58h+DestinationString]; String
0x180031810  call    cs:__imp_RtlHashUnicodeString
0x180031817  nop     dword ptr [rax+rax+00h]
0x18003181c  lea     ecx, [rdi+1]
0x18003181f  mov     word ptr [rbx+r14], 5Fh ; '_'
0x180031826  movsxd  rdx, ecx
0x180031829  mov     r9d, 10h
0x18003182f  mov     ecx, [rsp+58h+HashValue]
0x180031833  lea     rdx, [r14+rdx*2]
0x180031837  lea     r8d, [r9-7]
0x18003183b  call    cs:__imp__o__itow_s
0x180031842  nop     dword ptr [rax+rax+00h]
0x180031847  lea     r8, aSmbGlobalmappi; ".SMB-GlobalMapping-Target"
0x18003184e  mov     edx, 151h; cchDest
0x180031853  mov     rcx, r14; pszDest
0x180031856  call    StringCchCatW
0x18003185b  mov     eax, 1
0x180031860  jmp     short loc_180031864
0x180031862  xor     eax, eax
0x180031864  add     rsp, 38h
0x180031868  pop     r14
0x18003186a  pop     rdi
0x18003186b  pop     rsi
0x18003186c  pop     rbx
0x18003186d  retn
```
