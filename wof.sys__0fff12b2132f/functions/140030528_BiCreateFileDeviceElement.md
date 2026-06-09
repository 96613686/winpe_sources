# BiCreateFileDeviceElement

- ea: `0x140030528`
- end: `0x1400306f5`
- name: `BiCreateFileDeviceElement`
- size: `461`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400306fc`

## callees

- `0x14000da0d`
- `0x1400116c0`
- `0x1400119c0`
- `0x140030528`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x14003066c`
- `ntoskrnl!wcscpy_s` at `0x140030698`
- `ntoskrnl!wcscpy_s` at `0x14003066c`
- `ntoskrnl!wcscpy_s` at `0x140030698`
- `ntoskrnl!ExAllocatePool2` at `0x1400305a6`
- `ntoskrnl!ExAllocatePool2` at `0x14003061b`
- `ntoskrnl!ExAllocatePool2` at `0x1400305a6`
- `ntoskrnl!ExAllocatePool2` at `0x14003061b`
- `ntoskrnl!wcschr` at `0x140030574`
- `ntoskrnl!wcschr` at `0x140030574`
- `ntoskrnl!_wcsnicmp` at `0x140030556`
- `ntoskrnl!_wcsnicmp` at `0x140030556`

## pseudocode

```c
__int64 __fastcall BiCreateFileDeviceElement(const wchar_t *Src, _QWORD *a2, unsigned int *a3)
{
  wchar_t *v4; // rax
  const wchar_t *v5; // r14
  __int64 v6; // rbx
  char *Pool2; // rsi
  int v8; // ebx
  size_t v9; // rbx
  __int64 v10; // rbp
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // r15d
  unsigned int v14; // r13d
  char *v15; // rax
  char *v16; // rdi
  __int64 v17; // rdx

  if ( _wcsnicmp(Src, L"\\Device\\HarddiskVolume", 0x16u) )
    return (unsigned int)-1073741811;
  v4 = wcschr(Src + 22, 0x5Cu);
  if ( (v5 = v4) == 0 )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v6 = v4 - Src;
    Pool2 = (char *)ExAllocatePool2(258, 2LL * (unsigned int)(v6 + 1), 1262764866);
    if ( Pool2 )
    {
      v9 = 2LL * (unsigned int)v6;
      memmove(Pool2, Src, v9);
      v10 = -1;
      *(_WORD *)&Pool2[v9] = 0;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&Pool2[2 * v11] );
      v12 = -1;
      do
        ++v12;
      while ( v5[v12] );
      v13 = 2 * v12 + 46;
      v14 = v13 + 2 * (v11 + 11);
      v15 = (char *)ExAllocatePool2(258, v14, 1262764866);
      v16 = v15;
      if ( v15 )
      {
        v8 = 0;
        memset(v15, 0, v14);
        v17 = -1;
        *((_DWORD *)v16 + 5) = v13;
        *(_DWORD *)v16 = 3;
        do
          ++v17;
        while ( v5[v17] );
        wcscpy_s((wchar_t *)v16 + 12, v17 + 1, v5);
        *(_DWORD *)&v16[v13] = 2;
        do
          ++v10;
        while ( *(_WORD *)&Pool2[2 * v10] );
        wcscpy_s((wchar_t *)&v16[v13 + 20], v10 + 1, (const wchar_t *)Pool2);
        *a2 = v16;
        *a3 = v14;
      }
      else
      {
        v8 = -1073741670;
      }
      ExFreePoolWithTag_0(Pool2, 0x4B444342u);
      if ( v8 < 0 && v16 )
        ExFreePoolWithTag_0(v16, 0x4B444342u);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140030528  mov     [rsp+arg_0], rbx
0x14003052d  mov     [rsp+arg_10], r8
0x140030532  mov     [rsp+arg_8], rdx
0x140030537  push    rbp
0x140030538  push    rsi
0x140030539  push    rdi
0x14003053a  push    r12
0x14003053c  push    r13
0x14003053e  push    r14
0x140030540  push    r15
0x140030542  sub     rsp, 20h
0x140030546  mov     r8d, 16h; MaxCount
0x14003054c  lea     rdx, aDeviceHarddisk_1; "\\Device\\HarddiskVolume"
0x140030553  mov     rdi, rcx
0x140030556  call    cs:__imp__wcsnicmp
0x14003055d  nop     dword ptr [rax+rax+00h]
0x140030562  xor     r15d, r15d
0x140030565  test    eax, eax
0x140030567  jnz     loc_1400306D8
0x14003056d  lea     edx, [rax+5Ch]; Ch
0x140030570  lea     rcx, [rdi+2Ch]; Str
0x140030574  call    cs:__imp_wcschr
0x14003057b  nop     dword ptr [rax+rax+00h]
0x140030580  mov     r14, rax
0x140030583  test    rax, rax
0x140030586  jz      loc_1400306D8
0x14003058c  mov     rbx, rax
0x14003058f  mov     ecx, 102h
0x140030594  sub     rbx, rdi
0x140030597  mov     r8d, 4B444342h
0x14003059d  sar     rbx, 1
0x1400305a0  lea     edx, [rbx+1]
0x1400305a3  add     rdx, rdx
0x1400305a6  call    cs:__imp_ExAllocatePool2
0x1400305ad  nop     dword ptr [rax+rax+00h]
0x1400305b2  mov     rsi, rax
0x1400305b5  test    rax, rax
0x1400305b8  jnz     short loc_1400305C4
0x1400305ba  mov     ebx, 0C000009Ah
0x1400305bf  jmp     loc_1400306DD
0x1400305c4  mov     eax, ebx
0x1400305c6  mov     rdx, rdi; Src
0x1400305c9  mov     rcx, rsi; void *
0x1400305cc  lea     rbx, [rax+rax]
0x1400305d0  mov     r8, rbx; Size
0x1400305d3  call    memmove
0x1400305d8  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400305dc  mov     [rbx+rsi], r15w
0x1400305e1  mov     rdx, rbp
0x1400305e4  inc     rdx
0x1400305e7  cmp     [rsi+rdx*2], r15w
0x1400305ec  jnz     short loc_1400305E4
0x1400305ee  mov     rax, rbp
0x1400305f1  inc     rax
0x1400305f4  cmp     [r14+rax*2], r15w
0x1400305f9  jnz     short loc_1400305F1
0x1400305fb  lea     edx, [rdx+0Bh]
0x1400305fe  mov     r8d, 4B444342h
0x140030604  lea     r15d, ds:2Eh[rax*2]
0x14003060c  mov     ecx, 102h
0x140030611  lea     r13d, [r15+rdx*2]
0x140030615  mov     edx, r13d
0x140030618  mov     r12d, r13d
0x14003061b  call    cs:__imp_ExAllocatePool2
0x140030622  nop     dword ptr [rax+rax+00h]
0x140030627  mov     rdi, rax
0x14003062a  test    rax, rax
0x14003062d  jnz     short loc_140030636
0x14003062f  mov     ebx, 0C000009Ah
0x140030634  jmp     short loc_1400306B4
0x140030636  mov     r8, r12; Size
0x140030639  xor     edx, edx; Val
0x14003063b  mov     rcx, rdi; void *
0x14003063e  xor     ebx, ebx
0x140030640  call    memset
0x140030645  mov     r12d, r15d
0x140030648  mov     rdx, rbp
0x14003064b  mov     [rdi+14h], r15d
0x14003064f  xor     r15d, r15d
0x140030652  mov     dword ptr [rdi], 3
0x140030658  inc     rdx
0x14003065b  cmp     [r14+rdx*2], r15w
0x140030660  jnz     short loc_140030658
0x140030662  inc     rdx; SizeInWords
0x140030665  lea     rcx, [rdi+18h]; Dst
0x140030669  mov     r8, r14; Src
0x14003066c  call    cs:__imp_wcscpy_s
0x140030673  nop     dword ptr [rax+rax+00h]
0x140030678  mov     dword ptr [r12+rdi], 2
0x140030680  inc     rbp
0x140030683  cmp     [rsi+rbp*2], r15w
0x140030688  jnz     short loc_140030680
0x14003068a  lea     rcx, [rdi+14h]
0x14003068e  mov     r8, rsi; Src
0x140030691  add     rcx, r12; Dst
0x140030694  lea     rdx, [rbp+1]; SizeInWords
0x140030698  call    cs:__imp_wcscpy_s
0x14003069f  nop     dword ptr [rax+rax+00h]
0x1400306a4  mov     rax, [rsp+58h+arg_8]
0x1400306a9  mov     [rax], rdi
0x1400306ac  mov     rax, [rsp+58h+arg_10]
0x1400306b1  mov     [rax], r13d
0x1400306b4  mov     ebp, 4B444342h
0x1400306b9  mov     rcx, rsi; P
0x1400306bc  mov     edx, ebp; Tag
0x1400306be  call    ExFreePoolWithTag_0
0x1400306c3  test    ebx, ebx
0x1400306c5  jns     short loc_1400306DD
0x1400306c7  test    rdi, rdi
0x1400306ca  jz      short loc_1400306DD
0x1400306cc  mov     edx, ebp; Tag
0x1400306ce  mov     rcx, rdi; P
0x1400306d1  call    ExFreePoolWithTag_0
0x1400306d6  jmp     short loc_1400306DD
0x1400306d8  mov     ebx, 0C000000Dh
0x1400306dd  mov     eax, ebx
0x1400306df  mov     rbx, [rsp+58h+arg_0]
0x1400306e4  add     rsp, 20h
0x1400306e8  pop     r15
0x1400306ea  pop     r14
0x1400306ec  pop     r13
0x1400306ee  pop     r12
0x1400306f0  pop     rdi
0x1400306f1  pop     rsi
0x1400306f2  pop     rbp
0x1400306f3  retn
```
