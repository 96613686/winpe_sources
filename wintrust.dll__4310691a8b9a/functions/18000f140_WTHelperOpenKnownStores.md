# WTHelperOpenKnownStores

- ea: `0x18000f140`
- end: `0x18000f2d0`
- name: `WTHelperOpenKnownStores`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f684`
- `0x18000fea0`
- `0x180010f08`
- `0x180020458`

## callees

- `0x18000f140`
- `0x18000f310`
- `0x18000f450`
- `0x18000f580`
- `0x18002e5d0`
- `0x18002e5dc`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18000f228`
- `CRYPT32!CertOpenStore` at `0x18000f228`

## pseudocode

```c
__int64 __fastcall WTHelperOpenKnownStores(__int64 a1)
{
  __int64 v1; // rax
  _DWORD *v4; // rcx
  int v5; // eax
  HCERTSTORE Store; // rax
  void *pvPara; // [rsp+20h] [rbp-28h]

  v1 = *(_QWORD *)(a1 + 8);
  if ( !v1 )
    goto LABEL_2;
  if ( *(_DWORD *)(v1 + 32) != 5 )
    goto LABEL_2;
  v4 = *(_DWORD **)(v1 + 40);
  if ( *v4 <= 0x28u )
    goto LABEL_2;
  v5 = v4[10];
  if ( (v5 & 1) != 0 )
  {
    Store = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
    goto LABEL_8;
  }
  if ( (v5 & 2) == 0 )
  {
LABEL_2:
    TrustOpenStores(*(_QWORD *)(a1 + 40));
    return 0;
  }
  Store = (HCERTSTORE)StoreProviderGetStore(*(_QWORD *)(a1 + 40));
LABEL_8:
  if ( !Store )
    return 0;
  LODWORD(pvPara) = 8;
  AllocateNewChain(8u, (size_t)pvPara);
  return 1;
}

```

## disassembly

```asm
0x18000f140  mov     [rsp+arg_8], rbx
0x18000f145  mov     [rsp+arg_10], rbp
0x18000f14a  push    rsi
0x18000f14b  push    r14
0x18000f14d  push    r15
0x18000f14f  sub     rsp, 30h
0x18000f153  mov     rax, [rcx+8]
0x18000f157  mov     rbx, rcx
0x18000f15a  test    rax, rax
0x18000f15d  jnz     loc_18000F1F2
0x18000f163  mov     rcx, [rbx+28h]; hCryptProv
0x18000f167  lea     rdx, [rsp+48h+arg_0]
0x18000f16c  xor     r9d, r9d
0x18000f16f  mov     dword ptr [rsp+48h+arg_0], 0
0x18000f177  xor     r8d, r8d
0x18000f17a  call    TrustOpenStores
0x18000f17f  mov     eax, dword ptr [rsp+48h+arg_0]
0x18000f183  test    eax, eax
0x18000f185  jnz     short loc_18000F18B
0x18000f187  xor     eax, eax
0x18000f189  jmp     short loc_18000F1DE
0x18000f18b  mov     rcx, rax
0x18000f18e  mov     eax, 8
0x18000f193  mul     rcx
0x18000f196  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f19d  cmovb   rax, rcx
0x18000f1a1  mov     rcx, rax; unsigned __int64
0x18000f1a4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f1a9  mov     r14, rax
0x18000f1ac  test    rax, rax
0x18000f1af  jz      loc_18000F26D
0x18000f1b5  mov     rcx, [rbx+28h]; hCryptProv
0x18000f1b9  lea     rdx, [rsp+48h+arg_0]
0x18000f1be  xor     r9d, r9d
0x18000f1c1  mov     r8, rax
0x18000f1c4  call    TrustOpenStores
0x18000f1c9  test    eax, eax
0x18000f1cb  jnz     short loc_18000F230
0x18000f1cd  xor     esi, esi
0x18000f1cf  mov     rcx, r14; Block
0x18000f1d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f1d7  xor     eax, eax
0x18000f1d9  test    esi, esi
0x18000f1db  setnz   al
0x18000f1de  mov     rbx, [rsp+48h+arg_8]
0x18000f1e3  mov     rbp, [rsp+48h+arg_10]
0x18000f1e8  add     rsp, 30h
0x18000f1ec  pop     r15
0x18000f1ee  pop     r14
0x18000f1f0  pop     rsi
0x18000f1f1  retn
0x18000f1f2  cmp     dword ptr [rax+20h], 5
0x18000f1f6  jnz     loc_18000F163
0x18000f1fc  mov     rcx, [rax+28h]
0x18000f200  cmp     dword ptr [rcx], 28h ; '('
0x18000f203  jbe     loc_18000F163
0x18000f209  mov     eax, [rcx+28h]
0x18000f20c  test    al, 1
0x18000f20e  jz      loc_18000F2C6
0x18000f214  xor     edx, edx; dwEncodingType
0x18000f216  mov     [rsp+48h+pvPara], 0; pvPara
0x18000f21f  xor     r9d, r9d; dwFlags
0x18000f222  xor     r8d, r8d; hCryptProv
0x18000f225  lea     ecx, [rdx+2]; lpszStoreProvider
0x18000f228  call    cs:__imp_CertOpenStore
0x18000f22e  jmp     short loc_18000F28F
0x18000f230  mov     esi, dword ptr [rsp+48h+arg_0]
0x18000f234  xor     ebp, ebp
0x18000f236  test    esi, esi
0x18000f238  jz      short loc_18000F1CF
0x18000f23a  mov     rcx, [r14+rbp*8]
0x18000f23e  lea     r9, [rbx+60h]
0x18000f242  mov     [rsp+48h+arg_0], rcx
0x18000f247  lea     r8, [rbx+58h]
0x18000f24b  mov     ecx, 8; Size
0x18000f250  mov     dword ptr [rsp+48h+pvPara], 8; size_t
0x18000f258  lea     rdx, [rsp+48h+arg_0]
0x18000f25d  call    AllocateNewChain
0x18000f262  inc     ebp
0x18000f264  cmp     ebp, esi
0x18000f266  jb      short loc_18000F23A
0x18000f268  jmp     loc_18000F1CF
0x18000f26d  mov     rax, [rbx+50h]
0x18000f271  mov     dword ptr [rbx+30h], 8
0x18000f278  mov     dword ptr [rax+7Ch], 80096001h
0x18000f27f  jmp     loc_18000F187
0x18000f284  mov     rcx, [rbx+28h]; hCryptProv
0x18000f288  xor     edx, edx
0x18000f28a  call    StoreProviderGetStore
0x18000f28f  test    rax, rax
0x18000f292  jz      loc_18000F187
0x18000f298  lea     r9, [rbx+60h]
0x18000f29c  mov     [rsp+48h+arg_0], rax
0x18000f2a1  lea     r8, [rbx+58h]
0x18000f2a5  mov     dword ptr [rsp+48h+pvPara], 8; size_t
0x18000f2ad  lea     rdx, [rsp+48h+arg_0]
0x18000f2b2  mov     ecx, 8; Size
0x18000f2b7  call    AllocateNewChain
0x18000f2bc  mov     eax, 1
0x18000f2c1  jmp     loc_18000F1DE
0x18000f2c6  test    al, 2
0x18000f2c8  jz      loc_18000F163
0x18000f2ce  jmp     short loc_18000F284
```
