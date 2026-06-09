# SkpgHotpatchCreate

- ea: `0x1400a8944`
- end: `0x1400a8ce8`
- name: `SkpgHotpatchCreate`
- size: `932`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14001e71c`
- `0x1400455c4`
- `0x140049618`
- `0x14004a168`
- `0x1400817f0`
- `0x1400a8db4`

## callees

- `0x14000f0f0`
- `0x140013190`
- `0x140037e68`
- `0x1400a5308`
- `0x1400a8944`
- `0x1400a9410`
- `0x1400a96bc`
- `0x1400f3620`
- `0x1400f36e0`
- `0x1400f9780`
- `0x1400f9a80`

## import_xrefs

- `cng!BCryptCreateHash` at `0x1400a8ba8`
- `cng!BCryptCreateHash` at `0x1400a8ba8`

## pseudocode

```c
__int64 __fastcall SkpgHotpatchCreate(unsigned int a1, unsigned int *a2, int a3, __int64 *a4)
{
  __int64 v4; // rbx
  int v8; // r8d
  int v9; // r11d
  _BYTE *ImageExtents; // r13
  __int64 v12; // r12
  __int64 Pool; // r14
  __int64 v14; // rax
  __int64 v15; // rdi
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  size_t v20; // r8
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rax
  void *v23; // rsp
  const void *v24; // rdx
  void *v25; // rsp
  UCHAR *pbSecret; // r8
  NTSTATUS Hash; // edi
  void *v28; // rcx
  size_t v29; // r8
  unsigned int v30; // [rsp+40h] [rbp+0h] BYREF
  int v31; // [rsp+44h] [rbp+4h] BYREF
  __int64 v32; // [rsp+48h] [rbp+8h]
  PUCHAR v33; // [rsp+50h] [rbp+10h]
  __int64 *v34; // [rsp+58h] [rbp+18h]

  v4 = a1;
  v34 = a4;
  v30 = 0;
  v31 = 0;
  SkpgHotpatchLogEvent(SkpgContext, 512, (_DWORD)a2, a3, a1, 0);
  if ( !(unsigned int)SkpgIsInitialized() )
  {
    SkpgHotpatchLogEvent(SkpgContext, 513, v8, a3, v4, 0);
    *a4 = 0;
    return 0;
  }
  if ( (int)v4 < 0 )
  {
    v12 = *a2;
    ImageExtents = a2 + 6;
  }
  else
  {
    ImageExtents = (_BYTE *)SkpgLocateImageExtents((_DWORD)a2, v9, v4 & 1, (unsigned int)&v30, (__int64)&v31);
    if ( !ImageExtents )
    {
      if ( (v4 & 1) != 0 )
      {
        SkpgHotpatchLogEvent(SkpgContext, 514, (_DWORD)a2, a3, v4, 0);
        return 3221225781LL;
      }
      LODWORD(v4) = v4 | 0x40000000;
      SkpgHotpatchLogEvent(SkpgContext, 515, (_DWORD)a2, a3, (unsigned int)v4, 0);
    }
    v12 = v30;
  }
  v30 = 48 * v12 + 4 * (((unsigned int)v12 >> 5) + ((v12 & 0x1F) != 0)) + 87;
  Pool = SkAllocatePool(512, v30);
  if ( !Pool )
  {
    SkpgHotpatchLogEvent(SkpgContext, 516, (_DWORD)a2, a3, (unsigned int)v4, 0);
    return 3221225495LL;
  }
  v14 = SkpgContext;
  v15 = 0;
  v32 = SkpgContext;
  *(_QWORD *)(Pool + 16) = SkpgContext;
  if ( (v4 & 0x20000000) != 0 )
    v15 = (*(_DWORD *)(v14 + 244) >> 3) & 1;
  v16 = *(_DWORD *)(v14 + 4 * v15 + 200);
  *(_DWORD *)(Pool + 40) = v16;
  v17 = SkAllocatePool(512, v16);
  *(_QWORD *)(Pool + 32) = v17;
  if ( !v17 )
  {
    SkFreePool(512, Pool);
    SkpgHotpatchLogEvent(SkpgContext, 516, (_DWORD)a2, a3, (unsigned int)v4, 1);
    return 3221225495LL;
  }
  v18 = v32;
  v19 = *(unsigned int *)(v32 + 4 * v15 + 224);
  if ( (_DWORD)v19 )
  {
    v20 = (unsigned int)v19;
    v21 = v19 + 15;
    if ( v21 <= v20 )
      v21 = 0xFFFFFFFFFFFFFF0LL;
    v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
    v23 = alloca(v22);
    v24 = *(const void **)(v32 + 8 * v15 + 208);
    v25 = alloca(v22);
    v33 = (PUCHAR)&v30;
    memmove(&v30, v24, v20);
    v18 = v32;
    pbSecret = v33;
  }
  else
  {
    pbSecret = 0;
  }
  Hash = BCryptCreateHash(
           *(BCRYPT_ALG_HANDLE *)(v18 + 8 * v15 + 152),
           (BCRYPT_HASH_HANDLE *)(Pool + 24),
           *(PUCHAR *)(Pool + 32),
           *(_DWORD *)(Pool + 40),
           pbSecret,
           *(_DWORD *)(v18 + 4 * v15 + 224),
           0x20u);
  if ( Hash < 0 )
  {
    SkFreePool(512, *(_QWORD *)(Pool + 32));
    SkFreePool(512, Pool);
    SkpgHotpatchLogEvent(SkpgContext, 516, (_DWORD)a2, a3, (unsigned int)v4, 2);
    return (unsigned int)Hash;
  }
  *(_DWORD *)(Pool + 44) = v31;
  *(_DWORD *)(Pool + 48) = v30;
  *(_DWORD *)Pool = v4;
  *(_DWORD *)(Pool + 52) = ((Pool + 87) & 0xFFFFFFF0) - Pool;
  v28 = (void *)(48 * v12 + ((Pool + 87) & 0xFFFFFFFFFFFFFFF0uLL));
  *(_DWORD *)(Pool + 4) = v12;
  *(_QWORD *)(Pool + 8) = ImageExtents;
  v29 = 4 * ((unsigned int)v12 >> 5) + 4LL;
  *(_DWORD *)(Pool + 56) = v12;
  if ( (v12 & 0x1F) == 0 )
    v29 = 4 * ((unsigned int)v12 >> 5);
  *(_QWORD *)(Pool + 64) = v28;
  memset_0(v28, 0, v29);
  memmove((void *)((Pool + 87) & 0xFFFFFFFFFFFFFFF0uLL), ImageExtents, 48 * v12);
  for ( ; (_DWORD)v12; LODWORD(v12) = v12 - 1 )
  {
    if ( (ImageExtents[2] & 0x18) == 0 )
      SkpgBugCheckExecute(0x1105u, 0, 0, 0);
    ImageExtents += 48;
  }
  SkpgHotpatchLogEvent(SkpgContext, 517, (_DWORD)a2, a3, 0, Pool);
  *v34 = Pool;
  return 0;
}

```

## disassembly

```asm
0x1400a8944  push    rbp
0x1400a8946  push    rbx
0x1400a8947  push    rsi
0x1400a8948  push    rdi
0x1400a8949  push    r12
0x1400a894b  push    r13
0x1400a894d  push    r14
0x1400a894f  push    r15
0x1400a8951  sub     rsp, 78h
0x1400a8955  lea     rbp, [rsp+40h]
0x1400a895a  mov     rax, cs:__security_cookie
0x1400a8961  xor     rax, rbp
0x1400a8964  mov     [rbp+70h+var_50], rax
0x1400a8968  xor     r12d, r12d
0x1400a896b  mov     ebx, ecx
0x1400a896d  mov     rcx, cs:SkpgContext
0x1400a8974  mov     rdi, r9
0x1400a8977  mov     [rbp+70h+var_58], r9
0x1400a897b  mov     rsi, rdx
0x1400a897e  mov     r9d, r8d
0x1400a8981  mov     r11d, r8d
0x1400a8984  mov     r15d, r8d
0x1400a8987  mov     r8, rdx
0x1400a898a  mov     edx, 200h
0x1400a898f  mov     qword ptr [rsp+0B0h+cbSecret], r12
0x1400a8994  mov     [rbp+70h+var_70], r12d
0x1400a8998  mov     [rbp+70h+var_6C], r12d
0x1400a899c  mov     [rsp+0B0h+pbSecret], rbx
0x1400a89a1  call    SkpgHotpatchLogEvent
0x1400a89a6  call    SkpgIsInitialized
0x1400a89ab  test    eax, eax
0x1400a89ad  jnz     short loc_1400A89D5
0x1400a89af  mov     rcx, cs:SkpgContext
0x1400a89b6  mov     r9d, r15d
0x1400a89b9  mov     qword ptr [rsp+0B0h+cbSecret], r12
0x1400a89be  mov     edx, 201h
0x1400a89c3  mov     [rsp+0B0h+pbSecret], rbx
0x1400a89c8  call    SkpgHotpatchLogEvent
0x1400a89cd  mov     [rdi], r12
0x1400a89d0  jmp     loc_1400A8CB5
0x1400a89d5  test    ebx, ebx
0x1400a89d7  js      short loc_1400A8A4B
0x1400a89d9  lea     rax, [rbp+70h+var_6C]
0x1400a89dd  mov     edi, ebx
0x1400a89df  and     edi, 1
0x1400a89e2  mov     [rsp+0B0h+pbSecret], rax
0x1400a89e7  mov     r8d, edi
0x1400a89ea  lea     r9, [rbp+70h+var_70]
0x1400a89ee  mov     edx, r11d
0x1400a89f1  mov     rcx, rsi
0x1400a89f4  call    SkpgLocateImageExtents
0x1400a89f9  mov     r13, rax
0x1400a89fc  test    rax, rax
0x1400a89ff  jnz     short loc_1400A8A45
0x1400a8a01  mov     rcx, cs:SkpgContext
0x1400a8a08  mov     r9, r15
0x1400a8a0b  mov     qword ptr [rsp+0B0h+cbSecret], r12
0x1400a8a10  mov     r8, rsi
0x1400a8a13  test    edi, edi
0x1400a8a15  jz      short loc_1400A8A30
0x1400a8a17  mov     edx, 202h
0x1400a8a1c  mov     [rsp+0B0h+pbSecret], rbx
0x1400a8a21  call    SkpgHotpatchLogEvent
0x1400a8a26  mov     eax, 0C0000135h
0x1400a8a2b  jmp     loc_1400A8CB7
0x1400a8a30  bts     ebx, 1Eh
0x1400a8a34  mov     edx, 203h
0x1400a8a39  mov     eax, ebx
0x1400a8a3b  mov     [rsp+0B0h+pbSecret], rax
0x1400a8a40  call    SkpgHotpatchLogEvent
0x1400a8a45  mov     r12d, [rbp+70h+var_70]
0x1400a8a49  jmp     short loc_1400A8A52
0x1400a8a4b  mov     r12d, [rsi]
0x1400a8a4e  lea     r13, [rsi+18h]
0x1400a8a52  mov     ecx, 0
0x1400a8a57  lea     edx, [r12+r12*2]
0x1400a8a5b  shl     edx, 4
0x1400a8a5e  mov     eax, r12d
0x1400a8a61  test    r12b, 1Fh
0x1400a8a65  mov     r8d, 43486750h
0x1400a8a6b  setnz   cl
0x1400a8a6e  shr     eax, 5
0x1400a8a71  add     ecx, eax
0x1400a8a73  lea     eax, ds:57h[rcx*4]
0x1400a8a7a  mov     ecx, 200h
0x1400a8a7f  add     eax, edx
0x1400a8a81  mov     edx, eax
0x1400a8a83  mov     [rbp+70h+var_70], eax
0x1400a8a86  call    SkAllocatePool
0x1400a8a8b  mov     r14, rax
0x1400a8a8e  test    rax, rax
0x1400a8a91  jnz     short loc_1400A8AC0
0x1400a8a93  mov     qword ptr [rsp+0B0h+cbSecret], rax
0x1400a8a98  mov     rcx, cs:SkpgContext
0x1400a8a9f  mov     r9, r15
0x1400a8aa2  mov     eax, ebx
0x1400a8aa4  mov     r8, rsi
0x1400a8aa7  mov     edx, 204h
0x1400a8aac  mov     [rsp+0B0h+pbSecret], rax
0x1400a8ab1  call    SkpgHotpatchLogEvent
0x1400a8ab6  mov     eax, 0C0000017h
0x1400a8abb  jmp     loc_1400A8CB7
0x1400a8ac0  mov     rax, cs:SkpgContext
0x1400a8ac7  xor     edi, edi
0x1400a8ac9  mov     [rbp+70h+var_68], rax
0x1400a8acd  mov     [r14+10h], rax
0x1400a8ad1  bt      ebx, 1Dh
0x1400a8ad5  jnb     short loc_1400A8AE4
0x1400a8ad7  mov     edi, [rax+0F4h]
0x1400a8add  shr     rdi, 3
0x1400a8ae1  and     edi, 1
0x1400a8ae4  mov     eax, [rax+rdi*4+0C8h]
0x1400a8aeb  mov     ecx, 200h
0x1400a8af0  mov     edx, eax
0x1400a8af2  mov     [r14+28h], eax
0x1400a8af6  mov     r8d, 4F486750h
0x1400a8afc  call    SkAllocatePool
0x1400a8b01  mov     [r14+20h], rax
0x1400a8b05  test    rax, rax
0x1400a8b08  jnz     short loc_1400A8B25
0x1400a8b0a  mov     rdx, r14
0x1400a8b0d  mov     ecx, 200h
0x1400a8b12  call    SkFreePool
0x1400a8b17  mov     qword ptr [rsp+0B0h+cbSecret], 1
0x1400a8b20  jmp     loc_1400A8A98
0x1400a8b25  mov     rcx, [rbp+70h+var_68]
0x1400a8b29  mov     eax, [rcx+rdi*4+0E0h]
0x1400a8b30  test    eax, eax
0x1400a8b32  jz      short loc_1400A8B79
0x1400a8b34  mov     r8d, eax
0x1400a8b37  add     rax, 0Fh
0x1400a8b3b  cmp     rax, r8
0x1400a8b3e  ja      short loc_1400A8B4A
0x1400a8b40  mov     rax, 0FFFFFFFFFFFFFF0h
0x1400a8b4a  and     rax, 0FFFFFFFFFFFFFFF0h
0x1400a8b4e  call    _alloca_probe
0x1400a8b53  mov     rdx, [rcx+rdi*8+0D0h]; Src
0x1400a8b5b  sub     rsp, rax
0x1400a8b5e  lea     rax, [rsp+0B0h+var_70]
0x1400a8b63  mov     rcx, rax; void *
0x1400a8b66  mov     [rbp+70h+var_60], rax
0x1400a8b6a  call    memmove
0x1400a8b6f  mov     rcx, [rbp+70h+var_68]
0x1400a8b73  mov     r8, [rbp+70h+var_60]
0x1400a8b77  jmp     short loc_1400A8B7C
0x1400a8b79  xor     r8d, r8d
0x1400a8b7c  mov     eax, [rcx+rdi*4+0E0h]
0x1400a8b83  lea     rdx, [r14+18h]; phHash
0x1400a8b87  mov     r9d, [r14+28h]; cbHashObject
0x1400a8b8b  mov     rcx, [rcx+rdi*8+98h]; hAlgorithm
0x1400a8b93  mov     [rsp+0B0h+dwFlags], 20h ; ' '; dwFlags
0x1400a8b9b  mov     [rsp+0B0h+cbSecret], eax; cbSecret
0x1400a8b9f  mov     [rsp+0B0h+pbSecret], r8; pbSecret
0x1400a8ba4  mov     r8, [r14+20h]; pbHashObject
0x1400a8ba8  call    cs:__imp_BCryptCreateHash
0x1400a8baf  nop     dword ptr [rax+rax+00h]
0x1400a8bb4  mov     edi, eax
0x1400a8bb6  test    eax, eax
0x1400a8bb8  jns     short loc_1400A8C05
0x1400a8bba  mov     rdx, [r14+20h]
0x1400a8bbe  mov     r12d, 200h
0x1400a8bc4  mov     ecx, r12d
0x1400a8bc7  call    SkFreePool
0x1400a8bcc  mov     rdx, r14
0x1400a8bcf  mov     ecx, r12d
0x1400a8bd2  call    SkFreePool
0x1400a8bd7  mov     ecx, ebx
0x1400a8bd9  lea     edx, [r12+4]
0x1400a8bde  mov     qword ptr [rsp+0B0h+cbSecret], 2
0x1400a8be7  mov     r9, r15
0x1400a8bea  mov     [rsp+0B0h+pbSecret], rcx
0x1400a8bef  mov     r8, rsi
0x1400a8bf2  mov     rcx, cs:SkpgContext
0x1400a8bf9  call    SkpgHotpatchLogEvent
0x1400a8bfe  mov     eax, edi
0x1400a8c00  jmp     loc_1400A8CB7
0x1400a8c05  mov     eax, [rbp+70h+var_6C]
0x1400a8c08  lea     rdi, [r14+57h]
0x1400a8c0c  mov     [r14+2Ch], eax
0x1400a8c10  and     rdi, 0FFFFFFFFFFFFFFF0h
0x1400a8c14  mov     eax, [rbp+70h+var_70]
0x1400a8c17  mov     [r14+30h], eax
0x1400a8c1b  mov     eax, edi
0x1400a8c1d  sub     eax, r14d
0x1400a8c20  mov     [r14], ebx
0x1400a8c23  mov     [r14+34h], eax
0x1400a8c27  lea     rbx, [r12+r12*2]
0x1400a8c2b  mov     eax, r12d
0x1400a8c2e  shl     rbx, 4
0x1400a8c32  shr     eax, 5
0x1400a8c35  shl     eax, 2
0x1400a8c38  mov     edx, eax
0x1400a8c3a  test    r12b, 1Fh
0x1400a8c3e  lea     rcx, [rbx+rdi]; void *
0x1400a8c42  mov     [r14+4], r12d
0x1400a8c46  mov     [r14+8], r13
0x1400a8c4a  lea     r8, [rax+4]
0x1400a8c4e  mov     [r14+38h], r12d
0x1400a8c52  cmovz   r8, rdx; Size
0x1400a8c56  mov     [r14+40h], rcx
0x1400a8c5a  xor     edx, edx; Val
0x1400a8c5c  call    memset_0
0x1400a8c61  mov     r8, rbx; Size
0x1400a8c64  mov     rdx, r13; Src
0x1400a8c67  mov     rcx, rdi; void *
0x1400a8c6a  call    memmove
0x1400a8c6f  test    r12d, r12d
0x1400a8c72  jz      short loc_1400A8C87
0x1400a8c74  test    byte ptr [r13+2], 18h
0x1400a8c79  jz      short loc_1400A8CD5
0x1400a8c7b  add     r13, 30h ; '0'
0x1400a8c7f  add     r12d, 0FFFFFFFFh
0x1400a8c83  jnz     short loc_1400A8C74
0x1400a8c85  jmp     short loc_1400A8C8A
0x1400a8c87  xor     r12d, r12d
0x1400a8c8a  mov     rcx, cs:SkpgContext
0x1400a8c91  mov     r9, r15
0x1400a8c94  mov     eax, r12d
0x1400a8c97  mov     r8, rsi
0x1400a8c9a  mov     qword ptr [rsp+0B0h+cbSecret], r14
0x1400a8c9f  mov     edx, 205h
0x1400a8ca4  mov     [rsp+0B0h+pbSecret], rax
0x1400a8ca9  call    SkpgHotpatchLogEvent
0x1400a8cae  mov     rdx, [rbp+70h+var_58]
0x1400a8cb2  mov     [rdx], r14
0x1400a8cb5  xor     eax, eax
0x1400a8cb7  mov     rcx, [rbp+70h+var_50]
0x1400a8cbb  xor     rcx, rbp; StackCookie
0x1400a8cbe  call    __security_check_cookie
0x1400a8cc3  lea     rsp, [rbp+38h]
0x1400a8cc7  pop     r15
0x1400a8cc9  pop     r14
0x1400a8ccb  pop     r13
0x1400a8ccd  pop     r12
0x1400a8ccf  pop     rdi
0x1400a8cd0  pop     rsi
0x1400a8cd1  pop     rbx
0x1400a8cd2  pop     rbp
0x1400a8cd3  retn
0x1400a8cd5  xor     r9d, r9d; BugCheckParameter4
0x1400a8cd8  xor     r8d, r8d; BugCheckParameter3
0x1400a8cdb  xor     edx, edx; BugCheckParameter2
0x1400a8cdd  mov     ecx, 1105h; BugCheckParameter1
0x1400a8ce2  call    SkpgBugCheckExecute
```
