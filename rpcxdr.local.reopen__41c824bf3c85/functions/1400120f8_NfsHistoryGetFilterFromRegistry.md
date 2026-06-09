# NfsHistoryGetFilterFromRegistry

- ea: `0x1400120f8`
- end: `0x1400122a2`
- name: `NfsHistoryGetFilterFromRegistry`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140012468`

## callees

- `0x1400120f8`
- `0x1400122a8`
- `0x140013a68`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140012190`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140012190`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012268`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001228a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012268`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001228a`
- `ntoskrnl!ExAllocatePool2` at `0x140012130`
- `ntoskrnl!ExAllocatePool2` at `0x14001214c`
- `ntoskrnl!ExAllocatePool2` at `0x140012130`
- `ntoskrnl!ExAllocatePool2` at `0x14001214c`

## pseudocode

```c
__int64 __fastcall NfsHistoryGetFilterFromRegistry(__int64 a1)
{
  wchar_t *Pool2; // rax
  __int64 v3; // rcx
  PCHAR Buffer; // r8
  NTSTATUS String; // ebx
  unsigned int v6; // edi
  int v7; // ecx
  __int64 v8; // rdx
  unsigned int v9; // r10d
  __int64 i; // r11
  CHAR v11; // r9
  unsigned int j; // r11d
  __int64 v13; // rax
  unsigned int v14; // r9d
  struct _STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)&SourceString.Length = 6553600;
  *(_QWORD *)&DestinationString.Length = 3276800;
  DestinationString.Buffer = (PCHAR)ExAllocatePool2(66, 50, 1112754258);
  Pool2 = (wchar_t *)ExAllocatePool2(66, 100, 1113016402);
  Buffer = DestinationString.Buffer;
  SourceString.Buffer = Pool2;
  if ( DestinationString.Buffer && Pool2 )
  {
    String = NfsCfgMgrParameterGetString(v3, &SourceString);
    if ( String < 0 )
      goto LABEL_22;
    String = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 0);
    if ( String < 0 )
      goto LABEL_22;
    Buffer = DestinationString.Buffer;
    v6 = 0;
    v7 = 0;
    v8 = 0;
    v9 = 0;
    for ( i = 0; (unsigned int)i < DestinationString.Length; i = (unsigned int)(i + 1) )
    {
      if ( v6 >= 0xA )
        goto LABEL_24;
      v11 = Buffer[i];
      if ( !v11 )
        break;
      if ( v11 == 32 )
      {
        if ( v7 == 4 )
        {
          for ( j = v8; j < (int)v8 + 4; v9 = Buffer[v13] + (v9 << 8) )
            v13 = j++;
          NfsReferenceHistoryAddTypeInFilter(a1, _byteswap_ulong(v9), Buffer);
          Buffer = DestinationString.Buffer;
          ++v6;
        }
        v7 = 0;
        v8 = (unsigned int)(i + 1);
      }
      else
      {
        ++v7;
      }
    }
    if ( (unsigned int)(v7 - 1) <= 3 )
    {
      v14 = v8 + v7;
      while ( (unsigned int)v8 < v14 )
      {
        v9 = Buffer[v8] + (v9 << 8);
        v8 = (unsigned int)(v8 + 1);
      }
      NfsReferenceHistoryAddTypeInFilter(a1, _byteswap_ulong(v9), Buffer);
LABEL_22:
      Buffer = DestinationString.Buffer;
    }
  }
  else
  {
    String = -1073741670;
  }
LABEL_24:
  if ( Buffer )
  {
    ExFreePoolWithTag(Buffer, 0x42534852u);
    DestinationString.Buffer = 0;
  }
  if ( SourceString.Buffer )
    ExFreePoolWithTag(SourceString.Buffer, 0x42574852u);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1400120f8  push    rbp
0x1400120fa  push    rbx
0x1400120fb  push    rsi
0x1400120fc  push    rdi
0x1400120fd  mov     rbp, rsp
0x140012100  sub     rsp, 48h
0x140012104  mov     edx, 32h ; '2'
0x140012109  xorps   xmm0, xmm0
0x14001210c  xorps   xmm1, xmm1
0x14001210f  mov     rsi, rcx
0x140012112  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x140012116  mov     r8d, 42534852h
0x14001211c  lea     ebx, [rdx+10h]
0x14001211f  lea     eax, [rdx+32h]
0x140012122  mov     ecx, ebx
0x140012124  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140012128  mov     [rbp+DestinationString.MaximumLength], dx
0x14001212c  mov     [rbp+SourceString.MaximumLength], ax
0x140012130  call    cs:__imp_ExAllocatePool2
0x140012137  nop     dword ptr [rax+rax+00h]
0x14001213c  movzx   edx, [rbp+SourceString.MaximumLength]
0x140012140  mov     r8d, 42574852h
0x140012146  mov     ecx, ebx
0x140012148  mov     [rbp+DestinationString.Buffer], rax
0x14001214c  call    cs:__imp_ExAllocatePool2
0x140012153  nop     dword ptr [rax+rax+00h]
0x140012158  mov     r8, [rbp+DestinationString.Buffer]
0x14001215c  mov     [rbp+SourceString.Buffer], rax
0x140012160  test    r8, r8
0x140012163  jz      loc_140012256
0x140012169  test    rax, rax
0x14001216c  jz      loc_140012256
0x140012172  lea     rdx, [rbp+SourceString]
0x140012176  call    NfsCfgMgrParameterGetString
0x14001217b  mov     ebx, eax
0x14001217d  test    eax, eax
0x14001217f  js      loc_140012250
0x140012185  xor     r8d, r8d; AllocateDestinationString
0x140012188  lea     rdx, [rbp+SourceString]; SourceString
0x14001218c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012190  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140012197  nop     dword ptr [rax+rax+00h]
0x14001219c  mov     ebx, eax
0x14001219e  test    eax, eax
0x1400121a0  js      loc_140012250
0x1400121a6  mov     r8, [rbp+DestinationString.Buffer]
0x1400121aa  xor     edi, edi
0x1400121ac  xor     ecx, ecx
0x1400121ae  xor     edx, edx
0x1400121b0  xor     r10d, r10d
0x1400121b3  xor     r11d, r11d
0x1400121b6  movzx   eax, [rbp+DestinationString.Length]
0x1400121ba  cmp     r11d, eax
0x1400121bd  jnb     short loc_140012221
0x1400121bf  cmp     edi, 0Ah
0x1400121c2  jnb     loc_14001225B
0x1400121c8  mov     r9b, [r11+r8]
0x1400121cc  test    r9b, r9b
0x1400121cf  jz      short loc_140012221
0x1400121d1  cmp     r9b, 20h ; ' '
0x1400121d5  jnz     short loc_14001221A
0x1400121d7  cmp     ecx, 4
0x1400121da  jnz     short loc_140012212
0x1400121dc  lea     r9d, [rdx+4]
0x1400121e0  mov     r11d, edx
0x1400121e3  cmp     edx, r9d
0x1400121e6  jnb     short loc_1400121FF
0x1400121e8  mov     eax, r11d
0x1400121eb  inc     r11d
0x1400121ee  shl     r10d, 8
0x1400121f2  movsx   ecx, byte ptr [rax+r8]
0x1400121f7  add     r10d, ecx
0x1400121fa  cmp     r11d, r9d
0x1400121fd  jb      short loc_1400121E8
0x1400121ff  mov     edx, r10d
0x140012202  mov     rcx, rsi
0x140012205  bswap   edx
0x140012207  call    NfsReferenceHistoryAddTypeInFilter
0x14001220c  mov     r8, [rbp+DestinationString.Buffer]
0x140012210  inc     edi
0x140012212  xor     ecx, ecx
0x140012214  lea     edx, [r11+1]
0x140012218  jmp     short loc_14001221C
0x14001221a  inc     ecx
0x14001221c  inc     r11d
0x14001221f  jmp     short loc_1400121B6
0x140012221  lea     eax, [rcx-1]
0x140012224  cmp     eax, 3
0x140012227  ja      short loc_14001225B
0x140012229  lea     r9d, [rdx+rcx]
0x14001222d  jmp     short loc_14001223D
0x14001222f  movsx   ecx, byte ptr [rdx+r8]
0x140012234  shl     r10d, 8
0x140012238  add     r10d, ecx
0x14001223b  inc     edx
0x14001223d  cmp     edx, r9d
0x140012240  jb      short loc_14001222F
0x140012242  bswap   r10d
0x140012245  mov     edx, r10d
0x140012248  mov     rcx, rsi
0x14001224b  call    NfsReferenceHistoryAddTypeInFilter
0x140012250  mov     r8, [rbp+DestinationString.Buffer]
0x140012254  jmp     short loc_14001225B
0x140012256  mov     ebx, 0C000009Ah
0x14001225b  test    r8, r8
0x14001225e  jz      short loc_14001227C
0x140012260  mov     edx, 42534852h; Tag
0x140012265  mov     rcx, r8; P
0x140012268  call    cs:__imp_ExFreePoolWithTag
0x14001226f  nop     dword ptr [rax+rax+00h]
0x140012274  mov     [rbp+DestinationString.Buffer], 0
0x14001227c  mov     rcx, [rbp+SourceString.Buffer]; P
0x140012280  test    rcx, rcx
0x140012283  jz      short loc_140012296
0x140012285  mov     edx, 42574852h; Tag
0x14001228a  call    cs:__imp_ExFreePoolWithTag
0x140012291  nop     dword ptr [rax+rax+00h]
0x140012296  mov     eax, ebx
0x140012298  add     rsp, 48h
0x14001229c  pop     rdi
0x14001229d  pop     rsi
0x14001229e  pop     rbx
0x14001229f  pop     rbp
0x1400122a0  retn
```
