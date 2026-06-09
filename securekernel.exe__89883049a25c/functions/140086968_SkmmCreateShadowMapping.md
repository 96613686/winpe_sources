# SkmmCreateShadowMapping

- ea: `0x140086968`
- end: `0x140086c24`
- name: `SkmmCreateShadowMapping`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x14009a474`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x14000f0f0`
- `0x1400119c4`
- `0x140024724`
- `0x140033828`
- `0x1400355f4`
- `0x140037e68`
- `0x140050b48`
- `0x14007115c`
- `0x1400802ac`
- `0x140086968`
- `0x1400f3620`

## pseudocode

```c
__int64 __fastcall SkmmCreateShadowMapping(__int64 a1, ULONG_PTR a2, ULONG_PTR BugCheckParameter4, __int64 a4)
{
  unsigned __int64 v5; // r14
  int v6; // ebx
  unsigned __int64 v7; // r13
  __int64 v8; // rbp
  __int64 v9; // rsi
  __int64 v10; // rbx
  unsigned __int64 v11; // rdx
  int v12; // r8d
  unsigned __int64 v13; // rcx
  __int64 Pool; // r15
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rax
  char v19; // r13
  __int64 v20; // rdx
  __int64 v22; // [rsp+30h] [rbp-88h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-80h] BYREF
  __int64 v24; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v25[7]; // [rsp+48h] [rbp-70h]

  v22 = 0;
  v5 = a2;
  if ( (__int64 *)SkpsProcessList != &SkpsProcessList )
    SkeBugCheckEx(0x1Au, 0x56534Du, 0xB80u, a2, BugCheckParameter4);
  v6 = SkmiObtainPartition(0, &v22, 0, a4);
  if ( v6 >= 0 )
  {
    v7 = BugCheckParameter4 + v5 - 1;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    v11 = v7;
    v12 = 0;
    v13 = v5;
    do
    {
      v13 = ((v13 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
      v11 = ((v11 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
      if ( v12 )
        v10 += ((__int64)(v11 - v13) >> 3) + 1;
      ++v12;
    }
    while ( v12 <= 3 );
    Pool = SkAllocatePool(512, 8 * v10);
    v15 = SkAllocatePool(512, 0x18u);
    v16 = v15;
    if ( Pool && v15 )
    {
      v23 = 99;
      while ( (unsigned int)v8 < (unsigned int)v10 )
      {
        if ( !(unsigned int)SkmiAllocateZeroedPage(v22, &v23) )
        {
          v6 = -1073741670;
          goto LABEL_25;
        }
        *(_QWORD *)(Pool + 8 * v8) = (v23 >> 12) & 0xFFFFFFFFFFLL;
        v8 = (unsigned int)(v8 + 1);
      }
      *(_DWORD *)v16 = 0;
      v17 = 0;
      *(_DWORD *)(v16 + 4) = v8;
      *(_DWORD *)(v16 + 8) = v8;
      *(_QWORD *)(v16 + 16) = Pool;
      do
      {
        v5 = ((v5 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
        v7 = ((v7 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
        v18 = 2 * v17++;
        v25[v18 - 1] = v5;
        v25[v18] = v7;
      }
      while ( v17 != 4 );
      v23 = v7;
      v19 = SkAcquireSpinLockExclusive(&SkmiKernelPteLock);
      if ( (unsigned int)SkmiIsLeafPteValid(v24) && (unsigned int)SkmiIsLeafPteValid(v25[0]) )
      {
        SkmiMakeShadowPageTableRange(v5, v23, (unsigned int)&v24, 3, v16);
        v9 = (unsigned int)(*(_DWORD *)(v16 + 8) - *(_DWORD *)(v16 + 4));
        v6 = 0;
      }
      else
      {
        v6 = -1073741436;
      }
      if ( v19 != -1 )
      {
        LOBYTE(v20) = v19;
        SkReleaseSpinLockExclusive(&SkmiKernelPteLock, v20);
      }
    }
    else
    {
      v6 = -1073741670;
      if ( !Pool )
        goto LABEL_27;
    }
LABEL_25:
    while ( (unsigned int)v9 < (unsigned int)v8 )
    {
      SkmiFreePhysicalPage(v22, *(_QWORD *)(Pool + 8 * v9));
      v9 = (unsigned int)(v9 + 1);
    }
    SkFreePool(512, Pool);
LABEL_27:
    if ( v16 )
      SkFreePool(512, v16);
  }
  if ( v22 )
    SkmiDereferencePartition(v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140086968  mov     [rsp+arg_0], rbx
0x14008696d  mov     [rsp+arg_18], rbp
0x140086972  push    rsi
0x140086973  push    rdi
0x140086974  push    r13
0x140086976  push    r14
0x140086978  push    r15
0x14008697a  sub     rsp, 90h
0x140086981  mov     rax, cs:__security_cookie
0x140086988  xor     rax, rsp
0x14008698b  mov     [rsp+0B8h+var_38], rax
0x140086993  lea     rax, SkpsProcessList
0x14008699a  mov     [rsp+0B8h+var_88], 0
0x1400869a3  cmp     cs:SkpsProcessList, rax
0x1400869aa  mov     rdi, r8
0x1400869ad  mov     r14, rdx
0x1400869b0  jnz     loc_140086C06
0x1400869b6  xor     r8d, r8d
0x1400869b9  lea     rdx, [rsp+0B8h+var_88]
0x1400869be  xor     ecx, ecx
0x1400869c0  call    SkmiObtainPartition
0x1400869c5  mov     ebx, eax
0x1400869c7  test    eax, eax
0x1400869c9  js      loc_140086BC5
0x1400869cf  lea     r13, [r14-1]
0x1400869d3  mov     r9, 0FFFFF68000000000h
0x1400869dd  add     r13, rdi
0x1400869e0  xor     ebp, ebp
0x1400869e2  xor     esi, esi
0x1400869e4  xor     ebx, ebx
0x1400869e6  mov     rdx, r13
0x1400869e9  xor     r8d, r8d
0x1400869ec  mov     rcx, r14
0x1400869ef  mov     r10, 7FFFFFFFF8h
0x1400869f9  shr     rcx, 9
0x1400869fd  and     rcx, r10
0x140086a00  mov     rax, r9
0x140086a03  shr     rdx, 9
0x140086a07  add     rcx, rax
0x140086a0a  and     rdx, r10
0x140086a0d  mov     rax, r9
0x140086a10  add     rdx, rax
0x140086a13  cmp     r8d, 1
0x140086a17  jb      short loc_140086A29
0x140086a19  mov     rax, rdx
0x140086a1c  inc     rbx
0x140086a1f  sub     rax, rcx
0x140086a22  sar     rax, 3
0x140086a26  add     rbx, rax
0x140086a29  inc     r8d
0x140086a2c  cmp     r8d, 3
0x140086a30  jle     short loc_1400869F9
0x140086a32  mov     edi, 77536D4Dh
0x140086a37  lea     rdx, ds:0[rbx*8]
0x140086a3f  mov     r8d, edi
0x140086a42  mov     ecx, 200h
0x140086a47  call    SkAllocatePool
0x140086a4c  mov     r8d, edi
0x140086a4f  mov     edx, 18h
0x140086a54  mov     ecx, 200h
0x140086a59  mov     r15, rax
0x140086a5c  call    SkAllocatePool
0x140086a61  mov     rdi, rax
0x140086a64  test    r15, r15
0x140086a67  jz      loc_140086B86
0x140086a6d  test    rax, rax
0x140086a70  jz      loc_140086B86
0x140086a76  mov     [rsp+0B8h+var_80], 63h ; 'c'
0x140086a7f  cmp     ebp, ebx
0x140086a81  jnb     short loc_140086ABE
0x140086a83  mov     rcx, [rsp+0B8h+var_88]
0x140086a88  lea     rdx, [rsp+0B8h+var_80]
0x140086a8d  call    SkmiAllocateZeroedPage
0x140086a92  test    eax, eax
0x140086a94  jz      short loc_140086AB4
0x140086a96  mov     rcx, [rsp+0B8h+var_80]
0x140086a9b  mov     rax, 0FFFFFFFFFFh
0x140086aa5  shr     rcx, 0Ch
0x140086aa9  and     rcx, rax
0x140086aac  mov     [r15+rbp*8], rcx
0x140086ab0  inc     ebp
0x140086ab2  jmp     short loc_140086A7F
0x140086ab4  mov     ebx, 0C000009Ah
0x140086ab9  jmp     loc_140086BA2
0x140086abe  mov     [rdi], esi
0x140086ac0  xor     ecx, ecx
0x140086ac2  mov     [rdi+4], ebp
0x140086ac5  mov     r8, 7FFFFFFFF8h
0x140086acf  mov     [rdi+8], ebp
0x140086ad2  mov     [rdi+10h], r15
0x140086ad6  mov     rdx, 0FFFFF68000000000h
0x140086ae0  shr     r14, 9
0x140086ae4  and     r14, r8
0x140086ae7  mov     rax, rdx
0x140086aea  shr     r13, 9
0x140086aee  add     r14, rax
0x140086af1  and     r13, r8
0x140086af4  mov     rax, rdx
0x140086af7  add     r13, rax
0x140086afa  mov     rax, rcx
0x140086afd  add     rax, rax
0x140086b00  inc     rcx
0x140086b03  mov     [rsp+rax*8+0B8h+var_78], r14
0x140086b08  mov     [rsp+rax*8+0B8h+var_70], r13
0x140086b0d  cmp     rcx, 4
0x140086b11  jnz     short loc_140086AE0
0x140086b13  lea     rcx, SkmiKernelPteLock
0x140086b1a  mov     [rsp+0B8h+var_80], r13
0x140086b1f  call    SkAcquireSpinLockExclusive
0x140086b24  mov     rcx, [rsp+0B8h+var_78]
0x140086b29  mov     r13b, al
0x140086b2c  call    SkmiIsLeafPteValid
0x140086b31  test    eax, eax
0x140086b33  jz      short loc_140086B6A
0x140086b35  mov     rcx, [rsp+0B8h+var_70]
0x140086b3a  call    SkmiIsLeafPteValid
0x140086b3f  test    eax, eax
0x140086b41  jz      short loc_140086B6A
0x140086b43  mov     rdx, [rsp+0B8h+var_80]
0x140086b48  lea     r8, [rsp+0B8h+var_78]
0x140086b4d  mov     r9d, 3
0x140086b53  mov     [rsp+0B8h+BugCheckParameter4], rdi
0x140086b58  mov     rcx, r14
0x140086b5b  call    SkmiMakeShadowPageTableRange
0x140086b60  mov     esi, [rdi+8]
0x140086b63  sub     esi, [rdi+4]
0x140086b66  xor     ebx, ebx
0x140086b68  jmp     short loc_140086B6F
0x140086b6a  mov     ebx, 0C0000184h
0x140086b6f  cmp     r13b, 0FFh
0x140086b73  jz      short loc_140086BA2
0x140086b75  mov     dl, r13b
0x140086b78  lea     rcx, SkmiKernelPteLock
0x140086b7f  call    SkReleaseSpinLockExclusive
0x140086b84  jmp     short loc_140086BA2
0x140086b86  mov     ebx, 0C000009Ah
0x140086b8b  test    r15, r15
0x140086b8e  jz      short loc_140086BB3
0x140086b90  jmp     short loc_140086BA2
0x140086b92  mov     rdx, [r15+rsi*8]
0x140086b96  mov     rcx, [rsp+0B8h+var_88]
0x140086b9b  call    SkmiFreePhysicalPage
0x140086ba0  inc     esi
0x140086ba2  cmp     esi, ebp
0x140086ba4  jb      short loc_140086B92
0x140086ba6  mov     rdx, r15
0x140086ba9  mov     ecx, 200h
0x140086bae  call    SkFreePool
0x140086bb3  test    rdi, rdi
0x140086bb6  jz      short loc_140086BC5
0x140086bb8  mov     rdx, rdi
0x140086bbb  mov     ecx, 200h
0x140086bc0  call    SkFreePool
0x140086bc5  cmp     [rsp+0B8h+var_88], 0
0x140086bcb  jz      short loc_140086BD7
0x140086bcd  mov     rcx, [rsp+0B8h+var_88]
0x140086bd2  call    SkmiDereferencePartition
0x140086bd7  mov     eax, ebx
0x140086bd9  mov     rcx, [rsp+0B8h+var_38]
0x140086be1  xor     rcx, rsp; StackCookie
0x140086be4  call    __security_check_cookie
0x140086be9  lea     r11, [rsp+0B8h+var_28]
0x140086bf1  mov     rbx, [r11+30h]
0x140086bf5  mov     rbp, [r11+48h]
0x140086bf9  mov     rsp, r11
0x140086bfc  pop     r15
0x140086bfe  pop     r14
0x140086c00  pop     r13
0x140086c02  pop     rdi
0x140086c03  pop     rsi
0x140086c04  retn
0x140086c06  mov     r9, r14; BugCheckParameter3
0x140086c09  mov     [rsp+0B8h+BugCheckParameter4], rdi; BugCheckParameter4
0x140086c0e  mov     edx, 56534Dh; BugCheckParameter1
0x140086c13  mov     ecx, 1Ah; BugCheckCode
0x140086c18  mov     r8d, 0B80h; BugCheckParameter2
0x140086c1e  call    SkeBugCheckEx
```
