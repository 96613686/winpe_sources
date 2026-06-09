# SkmmCreateExposedSecureSection

- ea: `0x14005e710`
- end: `0x14005e981`
- name: `SkmmCreateExposedSecureSection`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x140014dd0`

## callees

- `0x140002ef0`
- `0x14000f0f0`
- `0x140012750`
- `0x140033a00`
- `0x14003492c`
- `0x140037e68`
- `0x140037e84`
- `0x140050634`
- `0x14005d8f4`
- `0x14005e710`
- `0x1400a1128`
- `0x1400a18a0`
- `0x1400a1950`
- `0x1400f9780`

## pseudocode

```c
__int64 __fastcall SkmmCreateExposedSecureSection(__int64 a1, __int64 a2, ULONG_PTR a3, unsigned int a4, __int64 *a5)
{
  __int64 v5; // rsi
  __int64 v6; // rdi
  int v9; // eax
  __int64 v10; // rbp
  int inited; // ebx
  __int64 v12; // rbx
  unsigned int v13; // r12d
  unsigned __int64 v14; // r14
  void *Pool; // rax
  __int64 v16; // r15
  int v17; // eax
  __int16 ProtectionMask; // ax
  __int64 v19; // rcx
  int v20; // r9d
  __int64 v21; // [rsp+30h] [rbp-68h] BYREF
  __int64 v22; // [rsp+38h] [rbp-60h] BYREF
  _OWORD *v23; // [rsp+40h] [rbp-58h] BYREF

  v5 = 0;
  v6 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  if ( ((a4 - 2) & 0xFFFFFFFD) != 0 )
    return 3221225485LL;
  if ( (*(_BYTE *)(a1 + 400) & 2) == 0 )
    return 3221225506LL;
  if ( (ShvlpHardwareFeatures & 0x80) == 0 )
    return 3225747457LL;
  v9 = SkmmMapDataTransfer(a2, a3, 1u, (ULONG_PTR *)&v21, 0);
  v10 = v21;
  inited = v9;
  if ( v9 >= 0 )
  {
    if ( *(_DWORD *)(v21 + 40) >= 0x30u )
    {
      v12 = *(_QWORD *)(v21 + 24);
      v13 = *(_DWORD *)(v12 + 44);
      LODWORD(v21) = *(_DWORD *)(v12 + 40);
      v14 = ((v13 & 0xFFF) + (unsigned __int64)(unsigned int)v21 + 4095) >> 12;
      if ( (_DWORD)v14
        && !*(_QWORD *)v12
        && v13 < 0x1000
        && (*(_BYTE *)(v12 + 10) & 0x16) != 0
        && 8 * v14 + 48 <= *(unsigned int *)(v10 + 40) )
      {
        Pool = (void *)SkAllocatePool(512, 8LL * (unsigned int)v14);
        v16 = (__int64)Pool;
        if ( !Pool )
        {
          inited = -1073741670;
          goto LABEL_28;
        }
        memmove(Pool, (const void *)(v12 + 48), 8LL * (unsigned int)v14);
        v17 = SkobCreateObjectEx(0, (__int64)&SkmiSectionType, 0, &v23);
        v5 = (__int64)v23;
        inited = v17;
        if ( v17 >= 0 )
        {
          *v23 = 0;
          *(_OWORD *)(v5 + 16) = 0;
          *(_QWORD *)(v5 + 32) = 0;
          *(_WORD *)(v5 + 16) = (v13 + v21) & 0xFFF;
          *(_WORD *)(v5 + 18) = v13;
          ProtectionMask = SkmiMakeProtectionMask(a4);
          LOBYTE(v19) = 1;
          *(_DWORD *)v5 = v20 ^ ((unsigned __int16)v20 ^ (unsigned __int16)(ProtectionMask << 9)) & 0x1E00;
          inited = SkobReserveHandle(v19, &v22);
          if ( inited < 0 )
          {
            v6 = v22;
          }
          else
          {
            v6 = v22;
            inited = SkmiInitSpecifyPagesSectionProtoPtes(v5, v16, v14, v22, 0);
            if ( inited >= 0 )
            {
              SkobReferenceObject(a1);
              *(_QWORD *)(v5 + 24) = a1;
              SkobMakeReservedHandleValid(v6, v5, 0);
              *a5 = v6;
              v6 = 0;
            }
          }
        }
        SkFreePool(512, v16);
      }
      else
      {
        inited = -1073741811;
      }
      if ( v6 )
        SkobDeleteReservedHandle(v6);
      if ( v5 )
        SkobDereferenceObject(v5);
      goto LABEL_28;
    }
    inited = -1073741811;
  }
LABEL_28:
  if ( v10 )
    SkmmUnmapDataTransfer(v10);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14005e710  mov     [rsp+arg_18], r9d
0x14005e715  push    rbx
0x14005e716  push    rbp
0x14005e717  push    rsi
0x14005e718  push    rdi
0x14005e719  push    r12
0x14005e71b  push    r13
0x14005e71d  push    r14
0x14005e71f  push    r15
0x14005e721  sub     rsp, 58h
0x14005e725  xor     esi, esi
0x14005e727  xor     edi, edi
0x14005e729  mov     eax, r9d
0x14005e72c  mov     [rsp+98h+var_58], rsi
0x14005e731  add     eax, 0FFFFFFFEh
0x14005e734  mov     [rsp+98h+var_60], rdi
0x14005e739  mov     [rsp+98h+var_68], rsi
0x14005e73e  mov     r10, r8
0x14005e741  mov     r11, rdx
0x14005e744  mov     r13, rcx
0x14005e747  test    eax, 0FFFFFFFDh
0x14005e74c  jz      short loc_14005E758
0x14005e74e  mov     eax, 0C000000Dh
0x14005e753  jmp     loc_14005E96F
0x14005e758  test    byte ptr [rcx+190h], 2
0x14005e75f  jnz     short loc_14005E76B
0x14005e761  mov     eax, 0C0000022h
0x14005e766  jmp     loc_14005E96F
0x14005e76b  mov     eax, dword ptr cs:ShvlpHardwareFeatures
0x14005e771  shr     eax, 7
0x14005e774  test    al, 1
0x14005e776  jnz     short loc_14005E782
0x14005e778  mov     eax, 0C0450001h
0x14005e77d  jmp     loc_14005E96F
0x14005e782  lea     r9, [rsp+98h+var_68]
0x14005e787  mov     [rsp+98h+var_78], rsi
0x14005e78c  mov     r8d, 1
0x14005e792  mov     rdx, r10
0x14005e795  mov     rcx, r11
0x14005e798  call    SkmmMapDataTransfer
0x14005e79d  mov     rbp, [rsp+98h+var_68]
0x14005e7a2  mov     ebx, eax
0x14005e7a4  test    eax, eax
0x14005e7a6  js      loc_14005E960
0x14005e7ac  cmp     dword ptr [rbp+28h], 30h ; '0'
0x14005e7b0  jnb     short loc_14005E7BC
0x14005e7b2  mov     ebx, 0C000000Dh
0x14005e7b7  jmp     loc_14005E960
0x14005e7bc  mov     rbx, [rbp+18h]
0x14005e7c0  mov     eax, [rbx+28h]
0x14005e7c3  mov     r12d, [rbx+2Ch]
0x14005e7c7  mov     ecx, r12d
0x14005e7ca  and     ecx, 0FFFh
0x14005e7d0  mov     dword ptr [rsp+98h+var_68], eax
0x14005e7d4  lea     r14, [rax+0FFFh]
0x14005e7db  add     r14, rcx
0x14005e7de  shr     r14, 0Ch
0x14005e7e2  test    r14d, r14d
0x14005e7e5  jz      loc_14005E941
0x14005e7eb  cmp     [rbx], rsi
0x14005e7ee  jnz     loc_14005E941
0x14005e7f4  cmp     r12d, 1000h
0x14005e7fb  jnb     loc_14005E941
0x14005e801  test    byte ptr [rbx+0Ah], 16h
0x14005e805  jz      loc_14005E941
0x14005e80b  mov     eax, [rbp+28h]
0x14005e80e  lea     rcx, ds:30h[r14*8]
0x14005e816  cmp     rcx, rax
0x14005e819  ja      loc_14005E941
0x14005e81f  mov     esi, r14d
0x14005e822  mov     r8d, 6E506D4Dh
0x14005e828  shl     rsi, 3
0x14005e82c  mov     ecx, 200h
0x14005e831  mov     rdx, rsi
0x14005e834  call    SkAllocatePool
0x14005e839  mov     r15, rax
0x14005e83c  test    rax, rax
0x14005e83f  jnz     short loc_14005E84B
0x14005e841  mov     ebx, 0C000009Ah
0x14005e846  jmp     loc_14005E960
0x14005e84b  lea     rdx, [rbx+30h]; Src
0x14005e84f  mov     r8, rsi; Size
0x14005e852  mov     rcx, r15; void *
0x14005e855  call    memmove
0x14005e85a  lea     r9, [rsp+98h+var_58]
0x14005e85f  xor     r8d, r8d
0x14005e862  lea     rdx, SkmiSectionType
0x14005e869  xor     ecx, ecx
0x14005e86b  call    SkobCreateObjectEx
0x14005e870  mov     rsi, [rsp+98h+var_58]
0x14005e875  mov     ebx, eax
0x14005e877  test    eax, eax
0x14005e879  js      loc_14005E932
0x14005e87f  xor     eax, eax
0x14005e881  xorps   xmm0, xmm0
0x14005e884  movups  xmmword ptr [rsi], xmm0
0x14005e887  mov     ecx, 0FFFh
0x14005e88c  movups  xmmword ptr [rsi+10h], xmm0
0x14005e890  mov     [rsi+20h], rax
0x14005e894  mov     eax, dword ptr [rsp+98h+var_68]
0x14005e898  add     ax, r12w
0x14005e89c  and     ax, cx
0x14005e89f  mov     ecx, [rsp+98h+arg_18]
0x14005e8a6  mov     [rsi+10h], ax
0x14005e8aa  mov     [rsi+12h], r12w
0x14005e8af  mov     r9d, [rsi]
0x14005e8b2  and     r9d, 0FFFFFFF1h
0x14005e8b6  or      r9d, 0A010h
0x14005e8bd  call    SkmiMakeProtectionMask
0x14005e8c2  shl     eax, 9
0x14005e8c5  lea     rdx, [rsp+98h+var_60]
0x14005e8ca  xor     eax, r9d
0x14005e8cd  mov     cl, 1
0x14005e8cf  and     eax, 1E00h
0x14005e8d4  xor     eax, r9d
0x14005e8d7  mov     [rsi], eax
0x14005e8d9  call    SkobReserveHandle
0x14005e8de  mov     ebx, eax
0x14005e8e0  test    eax, eax
0x14005e8e2  js      short loc_14005E92D
0x14005e8e4  mov     dword ptr [rsp+98h+var_78], edi
0x14005e8e8  mov     r8d, r14d
0x14005e8eb  mov     rdi, [rsp+98h+var_60]
0x14005e8f0  mov     rdx, r15
0x14005e8f3  mov     r9, rdi
0x14005e8f6  mov     rcx, rsi
0x14005e8f9  call    SkmiInitSpecifyPagesSectionProtoPtes
0x14005e8fe  mov     ebx, eax
0x14005e900  test    eax, eax
0x14005e902  js      short loc_14005E932
0x14005e904  mov     rcx, r13
0x14005e907  call    SkobReferenceObject
0x14005e90c  xor     r8d, r8d
0x14005e90f  mov     [rsi+18h], r13
0x14005e913  mov     rdx, rsi
0x14005e916  mov     rcx, rdi
0x14005e919  call    SkobMakeReservedHandleValid
0x14005e91e  mov     rax, [rsp+98h+arg_20]
0x14005e926  mov     [rax], rdi
0x14005e929  xor     edi, edi
0x14005e92b  jmp     short loc_14005E932
0x14005e92d  mov     rdi, [rsp+98h+var_60]
0x14005e932  mov     rdx, r15
0x14005e935  mov     ecx, 200h
0x14005e93a  call    SkFreePool
0x14005e93f  jmp     short loc_14005E946
0x14005e941  mov     ebx, 0C000000Dh
0x14005e946  test    rdi, rdi
0x14005e949  jz      short loc_14005E953
0x14005e94b  mov     rcx, rdi
0x14005e94e  call    SkobDeleteReservedHandle
0x14005e953  test    rsi, rsi
0x14005e956  jz      short loc_14005E960
0x14005e958  mov     rcx, rsi
0x14005e95b  call    SkobDereferenceObject
0x14005e960  test    rbp, rbp
0x14005e963  jz      short loc_14005E96D
0x14005e965  mov     rcx, rbp
0x14005e968  call    SkmmUnmapDataTransfer
0x14005e96d  mov     eax, ebx
0x14005e96f  add     rsp, 58h
0x14005e973  pop     r15
0x14005e975  pop     r14
0x14005e977  pop     r13
0x14005e979  pop     r12
0x14005e97b  pop     rdi
0x14005e97c  pop     rsi
0x14005e97d  pop     rbp
0x14005e97e  pop     rbx
0x14005e97f  retn
```
