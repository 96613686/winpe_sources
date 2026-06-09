# AddAEExtensionFields(NtsForNtpInfoInternal &,void *,ulong,ulong *)

- ea: `0x180057498`
- end: `0x1800576c6`
- name: `?AddAEExtensionFields@@YAJAEAUNtsForNtpInfoInternal@@PEAXKPEAK@Z`
- size: `558`
- prototype: `__int64 __fastcall(struct NtsForNtpInfoInternal *, char *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800577b4`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003dcaa`
- `0x18003dd2c`
- `0x180045abc`
- `0x180057498`
- `0x180057a0c`
- `0x180057a60`
- `0x18005acf0`
- `0x18005b018`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800575d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180057604`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800575d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180057604`
- `WS2_32!__imp_htons` at `0x180057574`
- `WS2_32!__imp_htons` at `0x18005758c`
- `WS2_32!__imp_htons` at `0x180057574`
- `WS2_32!__imp_htons` at `0x18005758c`

## string_xrefs

- `0x180057547`: `AddAEExtensionFields: Packet would be bigger than max NTS packet size. field length: %d currentOffset: %d\n`
- `0x1800575be`: `AddAEExtensionFields: GetNonceCounter failed\n`
- `0x18005766e`: `onecore\ds\security\services\w32time\nts\ntsextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AddAEExtensionFields(struct NtsForNtpInfoInternal *a1, char *a2, unsigned int a3, unsigned int *a4)
{
  __int64 v5; // r15
  __int64 v8; // r11
  size_t v9; // rbp
  unsigned int v10; // r8d
  int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // r14d
  unsigned int v14; // r12d
  char *v16; // rbx
  __int64 v17; // rbx
  unsigned __int64 NonceCounter; // rax
  unsigned __int64 *v19; // rbx
  int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  int v24; // [rsp+A0h] [rbp+18h]

  v5 = a3;
  v8 = *((_QWORD *)a1 + 26);
  v9 = *(unsigned int *)(v8 + 60);
  v10 = v9 + ((*(_DWORD *)(v8 + 60) & 3) != 0 ? 4 - (*(_DWORD *)(v8 + 60) & 3) : 0);
  v24 = *(_DWORD *)(v8 + 64);
  v11 = *(_DWORD *)(v8 + 60);
  if ( (unsigned int)v9 > 0x10 )
    v11 = 16;
  v12 = ((v11 & 3) != 0 ? 4 - (v11 & 3) : 0) + v11;
  v13 = v10 < v12 ? v12 - v10 : 0;
  v14 = v13 + ((*(_DWORD *)(v8 + 64) & 3) != 0 ? 4 - (*(_DWORD *)(v8 + 64) & 3) : 0) + v10 + *(_DWORD *)(v8 + 64) + 8;
  if ( v14 + (unsigned int)v5 >= 0x500 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"AddAEExtensionFields: Packet would be bigger than max NTS packet size. field length: %d currentOffset: %d\n",
        v14,
        (unsigned int)v5);
    return 2147942414LL;
  }
  v16 = &a2[v5];
  NtsExtFieldHeader::AddTypeAndLengthToExtensionField(&a2[v5], 1028, v14);
  *((_WORD *)v16 + 2) = htons(v9);
  *((_WORD *)v16 + 3) = htons(v24);
  v17 = (unsigned int)(v5 + 8);
  *a4 = v17;
  NonceCounter = AeadCryptoWrapper::GetNonceCounter(*((AeadCryptoWrapper **)a1 + 26));
  if ( !NonceCounter )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"AddAEExtensionFields: GetNonceCounter failed\n");
    return 2147500037LL;
  }
  v19 = (unsigned __int64 *)&a2[v17];
  if ( v19 )
  {
    if ( (unsigned int)v9 >= 8 )
    {
      *v19 = NonceCounter;
      goto LABEL_17;
    }
    memset_0(v19, 0, v9);
    *(_DWORD *)_o__errno() = 34;
  }
  else
  {
    *(_DWORD *)_o__errno() = 22;
  }
  invalid_parameter_noinfo();
LABEL_17:
  *a4 += v9;
  AddPaddingIfNeeded(v9, a2, *a4, a4);
  v20 = AeadCryptoWrapper::Encrypt(
          *((AeadCryptoWrapper **)a1 + 26),
          a2,
          *a4,
          a4,
          v5,
          (const unsigned __int8 *)v19,
          0,
          0);
  v21 = v20;
  if ( v20 >= 0 )
  {
    AddPaddingIfNeeded(*(_DWORD *)(*((_QWORD *)a1 + 26) + 64LL), a2, *a4, a4);
    if ( v13 )
    {
      memset_0(&a2[*a4], 0, v13);
      *a4 += v13;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntsextensions.cpp",
      (const char *)(unsigned int)v20,
      v22);
    return v21;
  }
}

```

## disassembly

```asm
0x180057498  push    rbx
0x18005749a  push    rbp
0x18005749b  push    rsi
0x18005749c  push    rdi
0x18005749d  push    r12
0x18005749f  push    r13
0x1800574a1  push    r14
0x1800574a3  push    r15
0x1800574a5  sub     rsp, 48h
0x1800574a9  mov     rdi, r9
0x1800574ac  mov     r15d, r8d
0x1800574af  mov     rsi, rdx
0x1800574b2  mov     r13, rcx
0x1800574b5  mov     r11, [rcx+0D0h]
0x1800574bc  mov     ebp, [r11+3Ch]
0x1800574c0  mov     eax, ebp
0x1800574c2  and     eax, 3
0x1800574c5  mov     ebx, 4
0x1800574ca  mov     r8d, ebx
0x1800574cd  sub     r8d, eax
0x1800574d0  neg     eax
0x1800574d2  sbb     eax, eax
0x1800574d4  and     r8d, eax
0x1800574d7  add     r8d, ebp
0x1800574da  mov     r9d, [r11+40h]
0x1800574de  mov     [rsp+88h+arg_10], r9d
0x1800574e6  mov     ecx, r9d
0x1800574e9  and     ecx, 3
0x1800574ec  mov     eax, ebx
0x1800574ee  sub     eax, ecx
0x1800574f0  neg     ecx
0x1800574f2  sbb     edx, edx
0x1800574f4  and     edx, eax
0x1800574f6  mov     ecx, ebp
0x1800574f8  lea     eax, [rbx+0Ch]
0x1800574fb  cmp     ebp, eax
0x1800574fd  cmova   ecx, eax
0x180057500  mov     eax, ecx
0x180057502  and     eax, 3
0x180057505  sub     ebx, eax
0x180057507  neg     eax
0x180057509  sbb     eax, eax
0x18005750b  and     eax, ebx
0x18005750d  add     ecx, eax
0x18005750f  mov     eax, ecx
0x180057511  sub     eax, r8d
0x180057514  cmp     r8d, ecx
0x180057517  sbb     r14d, r14d
0x18005751a  and     r14d, eax
0x18005751d  lea     eax, [rdx+r8]
0x180057521  add     eax, r14d
0x180057524  lea     r12d, [r9+8]
0x180057528  add     r12d, eax
0x18005752b  lea     eax, [r12+r15]
0x18005752f  cmp     eax, 500h
0x180057534  jb      short loc_18005755D
0x180057536  xor     ecx, ecx
0x180057538  call    FileLogAllowEntry
0x18005753d  test    al, al
0x18005753f  jz      short loc_180057553
0x180057541  mov     r8d, r15d
0x180057544  mov     edx, r12d
0x180057547  lea     rcx, aAddaeextension; "AddAEExtensionFields: Packet would be b"...
0x18005754e  call    FileLogAdd
0x180057553  mov     eax, 8007000Eh
0x180057558  jmp     loc_1800576B4
0x18005755d  lea     rbx, [rsi+r15]
0x180057561  mov     r8d, r12d
0x180057564  mov     edx, 404h
0x180057569  mov     rcx, rbx
0x18005756c  call    ?AddTypeAndLengthToExtensionField@NtsExtFieldHeader@@QEAAXW4NtsExtFieldType@@K@Z; NtsExtFieldHeader::AddTypeAndLengthToExtensionField(NtsExtFieldType,ulong)
0x180057571  movzx   ecx, bp; hostshort
0x180057574  call    cs:__imp_htons
0x18005757b  nop     dword ptr [rax+rax+00h]
0x180057580  mov     [rbx+4], ax
0x180057584  movzx   ecx, word ptr [rsp+88h+arg_10]; hostshort
0x18005758c  call    cs:__imp_htons
0x180057593  nop     dword ptr [rax+rax+00h]
0x180057598  mov     [rbx+6], ax
0x18005759c  lea     ebx, [r15+8]
0x1800575a0  mov     [rdi], ebx
0x1800575a2  mov     rcx, [r13+0D0h]; this
0x1800575a9  call    ?GetNonceCounter@AeadCryptoWrapper@@QEAA_KXZ; AeadCryptoWrapper::GetNonceCounter(void)
0x1800575ae  test    rax, rax
0x1800575b1  jnz     short loc_1800575D4
0x1800575b3  xor     ecx, ecx
0x1800575b5  call    FileLogAllowEntry
0x1800575ba  test    al, al
0x1800575bc  jz      short loc_1800575CA
0x1800575be  lea     rcx, aAddaeextension_0; "AddAEExtensionFields: GetNonceCounter f"...
0x1800575c5  call    FileLogAdd
0x1800575ca  mov     eax, 80004005h
0x1800575cf  jmp     loc_1800576B4
0x1800575d4  add     rbx, rsi
0x1800575d7  jnz     short loc_1800575ED
0x1800575d9  call    cs:__imp__o__errno
0x1800575e0  nop     dword ptr [rax+rax+00h]
0x1800575e5  mov     dword ptr [rax], 16h
0x1800575eb  jmp     short loc_180057616
0x1800575ed  cmp     ebp, 8
0x1800575f0  jb      short loc_1800575F7
0x1800575f2  mov     [rbx], rax
0x1800575f5  jmp     short loc_18005761B
0x1800575f7  mov     r8, rbp; Size
0x1800575fa  xor     edx, edx; Val
0x1800575fc  mov     rcx, rbx; void *
0x1800575ff  call    memset_0
0x180057604  call    cs:__imp__o__errno
0x18005760b  nop     dword ptr [rax+rax+00h]
0x180057610  mov     dword ptr [rax], 22h ; '"'
0x180057616  call    _invalid_parameter_noinfo
0x18005761b  add     [rdi], ebp
0x18005761d  mov     r9, rdi; unsigned int *
0x180057620  mov     r8d, [rdi]; unsigned int
0x180057623  mov     rdx, rsi; void *
0x180057626  mov     ecx, ebp; unsigned int
0x180057628  call    ?AddPaddingIfNeeded@@YAXKPEAXKPEAK@Z; AddPaddingIfNeeded(ulong,void *,ulong,ulong *)
0x18005762d  mov     [rsp+88h+var_50], 0; unsigned int
0x180057635  mov     [rsp+88h+var_58], 0; unsigned __int8 *
0x18005763e  mov     [rsp+88h+var_60], rbx; unsigned __int8 *
0x180057643  mov     [rsp+88h+var_68], r15d; int
0x180057648  mov     r9, rdi; unsigned int *
0x18005764b  mov     r8d, [rdi]; unsigned int
0x18005764e  mov     rdx, rsi; void *
0x180057651  mov     rcx, [r13+0D0h]; this
0x180057658  call    ?Encrypt@AeadCryptoWrapper@@UEAAJPEAXKPEAKKPEBEPEAEK@Z; AeadCryptoWrapper::Encrypt(void *,ulong,ulong *,ulong,uchar const *,uchar *,ulong)
0x18005765d  mov     ebx, eax
0x18005765f  test    eax, eax
0x180057661  jns     short loc_180057683
0x180057663  mov     rcx, [rsp+88h]; this
0x18005766b  mov     r9d, eax; char *
0x18005766e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\w32tim"...
0x180057675  mov     edx, 0AAh; void *
0x18005767a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005767f  mov     eax, ebx
0x180057681  jmp     short loc_1800576B4
0x180057683  mov     rcx, [r13+0D0h]
0x18005768a  mov     r9, rdi; unsigned int *
0x18005768d  mov     r8d, [rdi]; unsigned int
0x180057690  mov     rdx, rsi; void *
0x180057693  mov     ecx, [rcx+40h]; unsigned int
0x180057696  call    ?AddPaddingIfNeeded@@YAXKPEAXKPEAK@Z; AddPaddingIfNeeded(ulong,void *,ulong,ulong *)
0x18005769b  test    r14d, r14d
0x18005769e  jz      short loc_1800576B2
0x1800576a0  mov     r8d, r14d; Size
0x1800576a3  mov     ecx, [rdi]
0x1800576a5  add     rcx, rsi; void *
0x1800576a8  xor     edx, edx; Val
0x1800576aa  call    memset_0
0x1800576af  add     [rdi], r14d
0x1800576b2  xor     eax, eax
0x1800576b4  add     rsp, 48h
0x1800576b8  pop     r15
0x1800576ba  pop     r14
0x1800576bc  pop     r13
0x1800576be  pop     r12
0x1800576c0  pop     rdi
0x1800576c1  pop     rsi
0x1800576c2  pop     rbp
0x1800576c3  pop     rbx
0x1800576c4  retn
```
