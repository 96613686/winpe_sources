# SkobCreateObjectEx

- ea: `0x1400a18a0`
- end: `0x1400a194a`
- name: `SkobCreateObjectEx`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `4`
- tags: ``

## callers

- `0x14004444c`
- `0x1400500b4`
- `0x14005c1e0`
- `0x14005e710`
- `0x14005e988`
- `0x140062a88`
- `0x14006b310`
- `0x14008969c`
- `0x140089b8c`
- `0x14009760c`
- `0x140097804`
- `0x140098abc`
- `0x1400a1880`
- `0x1400ad0a4`
- `0x1400ae210`
- `0x1400b48c4`

## callees

- `0x14000f0f0`
- `0x140037e68`
- `0x1400a18a0`
- `0x1400a1a40`

## pseudocode

```c
__int64 __fastcall SkobCreateObjectEx(char a1, __int64 a2, unsigned __int64 a3, _QWORD *a4)
{
  unsigned __int64 v5; // rdi
  __int64 Pool; // rax
  __int64 v9; // rcx
  __int64 v10; // rbx

  v5 = a3;
  Pool = SkAllocatePool(512, *(unsigned int *)(a2 + 8) + (((unsigned __int128)-(__int128)a3 >> 64) & 0x50) + 32);
  v10 = Pool;
  if ( !Pool )
    return 3221225626LL;
  if ( !v5 )
  {
    *(_BYTE *)(Pool + 8) = 0;
    goto LABEL_8;
  }
  LOBYTE(v9) = a1;
  LODWORD(v5) = SkobpCaptureObjectIdentity(v9, v5, Pool);
  if ( (v5 & 0x80000000) == 0LL )
  {
    v10 += 80;
    *(_BYTE *)(v10 + 8) = 1;
LABEL_8:
    *(_QWORD *)v10 = 1397444418;
    *(_QWORD *)(v10 + 24) = 1;
    *(_QWORD *)(v10 + 16) = a2;
    *a4 = v10 + 32;
    return (unsigned int)v5;
  }
  SkFreePool(512, v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400a18a0  push    rbx
0x1400a18a2  push    rbp
0x1400a18a3  push    rsi
0x1400a18a4  push    rdi
0x1400a18a5  push    r14
0x1400a18a7  sub     rsp, 20h
0x1400a18ab  mov     rsi, rdx
0x1400a18ae  mov     rax, r8
0x1400a18b1  neg     rax
0x1400a18b4  mov     rdi, r8
0x1400a18b7  mov     bpl, cl
0x1400a18ba  mov     r8d, 206A624Fh
0x1400a18c0  sbb     rdx, rdx
0x1400a18c3  mov     ecx, 200h
0x1400a18c8  mov     eax, [rsi+8]
0x1400a18cb  and     edx, 50h
0x1400a18ce  add     rdx, 20h ; ' '
0x1400a18d2  mov     r14, r9
0x1400a18d5  add     rdx, rax
0x1400a18d8  call    SkAllocatePool
0x1400a18dd  mov     rbx, rax
0x1400a18e0  test    rax, rax
0x1400a18e3  jnz     short loc_1400A18EC
0x1400a18e5  mov     eax, 0C000009Ah
0x1400a18ea  jmp     short loc_1400A193E
0x1400a18ec  test    rdi, rdi
0x1400a18ef  jz      short loc_1400A191E
0x1400a18f1  mov     r8, rbx
0x1400a18f4  mov     rdx, rdi
0x1400a18f7  mov     cl, bpl
0x1400a18fa  call    SkobpCaptureObjectIdentity
0x1400a18ff  mov     edi, eax
0x1400a1901  test    eax, eax
0x1400a1903  js      short loc_1400A190F
0x1400a1905  add     rbx, 50h ; 'P'
0x1400a1909  mov     byte ptr [rbx+8], 1
0x1400a190d  jmp     short loc_1400A1922
0x1400a190f  mov     rdx, rbx
0x1400a1912  mov     ecx, 200h
0x1400a1917  call    SkFreePool
0x1400a191c  jmp     short loc_1400A193C
0x1400a191e  mov     [rax+8], dil
0x1400a1922  lea     rax, [rbx+20h]
0x1400a1926  mov     qword ptr [rbx], 534B4F42h
0x1400a192d  mov     qword ptr [rbx+18h], 1
0x1400a1935  mov     [rbx+10h], rsi
0x1400a1939  mov     [r14], rax
0x1400a193c  mov     eax, edi
0x1400a193e  add     rsp, 20h
0x1400a1942  pop     r14
0x1400a1944  pop     rdi
0x1400a1945  pop     rsi
0x1400a1946  pop     rbp
0x1400a1947  pop     rbx
0x1400a1948  retn
```
