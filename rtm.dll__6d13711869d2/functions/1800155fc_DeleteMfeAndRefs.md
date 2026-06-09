# DeleteMfeAndRefs

- ea: `0x1800155fc`
- end: `0x1800157e3`
- name: `DeleteMfeAndRefs`
- size: `487`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800158cc`
- `0x180015a8c`
- `0x180015f54`

## callees

- `0x180014d2c`
- `0x180015178`
- `0x1800155fc`
- `0x1800157ec`
- `0x18001bc4c`
- `0x18001decc`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001572b`
- `KERNEL32!HeapFree` at `0x1800157b9`
- `KERNEL32!HeapFree` at `0x18001572b`
- `KERNEL32!HeapFree` at `0x1800157b9`

## pseudocode

```c
int __fastcall DeleteMfeAndRefs(unsigned int *lpMem)
{
  __int64 v2; // rdx
  int result; // eax
  __int64 v4; // rsi
  unsigned int v5; // r8d
  __int64 v6; // r9
  void *v7; // r8
  _QWORD *v8; // rax
  LPVOID *v9; // rcx
  __int64 v10; // r8
  const wchar_t *v11; // rdx
  int v12; // [rsp+20h] [rbp-E0h]
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMema; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v13 = 0;
  v14 = 0;
  v17 = 0;
  v15 = 0;
  lpMema = 0;
  memset_0(v18, 0, sizeof(v18));
  result = LookupAndDeleteYourMfe(lpMem[6], v2, lpMem[4], lpMem[5], v12, &v13, (__int64)&v14, 0);
  if ( v13 )
  {
    v4 = 32LL * (v13 % dword_18002B92C);
    AcquireWriteLock((char *)qword_18002B9E8 + v4 + 16);
    if ( (unsigned int)FindIfEntry((char *)qword_18002B9E8 + v4, v13, v14, &v15) )
    {
      if ( (unsigned int)FindRefEntry((int)v15 + 56, lpMem[6], v5, lpMem[4]) )
      {
        v7 = lpMema;
        v8 = *(_QWORD **)lpMema;
        if ( *(LPVOID *)(*(_QWORD *)lpMema + 8LL) != lpMema || (v9 = (LPVOID *)*((_QWORD *)lpMema + 1), *v9 != lpMema) )
          __fastfail(3u);
        *v9 = v8;
        v8[1] = v9;
        HeapFree(hHeap, 0, v7);
        goto LABEL_13;
      }
      if ( qword_18002B8A8 )
      {
        v10 = lpMem[6];
        v11 = L"Could not find ref entry for %x, %x";
LABEL_12:
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v17, v11, v10, v6);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v17);
      }
    }
    else if ( qword_18002B8A8 )
    {
      v6 = v5;
      v11 = L"Could not find i/f entry for %x, %x";
      v10 = v13;
      goto LABEL_12;
    }
LABEL_13:
    ReleaseWriteLock((__int64)qword_18002B9E8 + v4 + 16);
    return HeapFree(hHeap, 0, lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x1800155fc  mov     [rsp-8+arg_8], rbx
0x180015601  mov     [rsp-8+arg_10], rsi
0x180015606  push    rbp
0x180015607  lea     rbp, [rsp-770h]
0x18001560f  sub     rsp, 870h
0x180015616  mov     rax, cs:__security_cookie
0x18001561d  xor     rax, rsp
0x180015620  mov     [rbp+770h+var_10], rax
0x180015627  mov     rbx, rcx
0x18001562a  mov     [rsp+870h+var_830], 0
0x180015632  xor     eax, eax
0x180015634  mov     [rsp+870h+var_82C], 0
0x18001563c  lea     rcx, [rsp+870h+var_80C]; void *
0x180015641  mov     [rsp+870h+var_810], eax
0x180015645  xor     edx, edx; Val
0x180015647  mov     [rsp+870h+var_828], 0
0x180015650  mov     r8d, 7FCh; Size
0x180015656  mov     [rsp+870h+lpMem], 0
0x18001565f  call    memset_0
0x180015664  mov     r9d, [rbx+14h]
0x180015668  lea     rax, [rsp+870h+var_82C]
0x18001566d  mov     r8d, [rbx+10h]
0x180015671  mov     ecx, [rbx+18h]
0x180015674  mov     [rsp+870h+var_838], 0
0x18001567c  mov     [rsp+870h+var_840], rax
0x180015681  lea     rax, [rsp+870h+var_830]
0x180015686  mov     [rsp+870h+var_848], rax
0x18001568b  call    LookupAndDeleteYourMfe
0x180015690  cmp     [rsp+870h+var_830], 0
0x180015695  jz      loc_1800157BF
0x18001569b  mov     eax, [rsp+870h+var_830]
0x18001569f  xor     edx, edx
0x1800156a1  div     cs:dword_18002B92C
0x1800156a7  mov     rcx, cs:qword_18002B9E8
0x1800156ae  mov     esi, edx
0x1800156b0  add     rcx, 10h
0x1800156b4  shl     rsi, 5
0x1800156b8  add     rcx, rsi
0x1800156bb  call    AcquireWriteLock
0x1800156c0  mov     rcx, cs:qword_18002B9E8
0x1800156c7  lea     r9, [rsp+870h+var_828]
0x1800156cc  mov     edx, [rsp+870h+var_830]
0x1800156d0  add     rcx, rsi
0x1800156d3  mov     r8d, [rsp+870h+var_82C]
0x1800156d8  call    FindIfEntry
0x1800156dd  test    eax, eax
0x1800156df  jz      short loc_180015751
0x1800156e1  mov     rcx, [rsp+870h+var_828]
0x1800156e6  lea     rax, [rsp+870h+lpMem]
0x1800156eb  mov     edx, [rbx+18h]
0x1800156ee  add     rcx, 38h ; '8'
0x1800156f2  mov     r9d, [rbx+10h]
0x1800156f6  mov     [rsp+870h+var_848], rax
0x1800156fb  call    FindRefEntry
0x180015700  test    eax, eax
0x180015702  jz      short loc_18001573A
0x180015704  mov     r8, [rsp+870h+lpMem]; lpMem
0x180015709  mov     rax, [r8]
0x18001570c  cmp     [rax+8], r8
0x180015710  jnz     short loc_180015733
0x180015712  mov     rcx, [r8+8]
0x180015716  cmp     [rcx], r8
0x180015719  jnz     short loc_180015733
0x18001571b  mov     [rcx], rax
0x18001571e  xor     edx, edx; dwFlags
0x180015720  mov     [rax+8], rcx
0x180015724  mov     rcx, cs:hHeap; hHeap
0x18001572b  call    cs:__imp_HeapFree
0x180015731  jmp     short loc_18001579A
0x180015733  mov     ecx, 3
0x180015738  int     29h; Win8: RtlFailFast(ecx)
0x18001573a  cmp     cs:qword_18002B8A8, 0
0x180015742  jz      short loc_18001579A
0x180015744  mov     r8d, [rbx+18h]
0x180015748  lea     rdx, aCouldNotFindRe; "Could not find ref entry for %x, %x"
0x18001574f  jmp     short loc_18001576A
0x180015751  cmp     cs:qword_18002B8A8, 0
0x180015759  jz      short loc_18001579A
0x18001575b  mov     r9d, r8d
0x18001575e  lea     rdx, aCouldNotFindIF; "Could not find i/f entry for %x, %x"
0x180015765  mov     r8d, [rsp+870h+var_830]
0x18001576a  xor     eax, eax
0x18001576c  lea     rcx, [rsp+870h+var_810]
0x180015771  mov     word ptr [rsp+870h+var_810], ax
0x180015776  call    FormatRRASErrorString
0x18001577b  mov     rdx, cs:qword_18002B8A8
0x180015782  lea     r8, [rsp+870h+var_810]
0x180015787  mov     rcx, cs:gMgmEtwContext
0x18001578e  mov     rax, cs:gMgmTemplateFunc
0x180015795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001579a  mov     rcx, cs:qword_18002B9E8
0x1800157a1  add     rcx, 10h
0x1800157a5  add     rcx, rsi
0x1800157a8  call    ReleaseWriteLock
0x1800157ad  mov     rcx, cs:hHeap; hHeap
0x1800157b4  mov     r8, rbx; lpMem
0x1800157b7  xor     edx, edx; dwFlags
0x1800157b9  call    cs:__imp_HeapFree
0x1800157bf  mov     rcx, [rbp+770h+var_10]
0x1800157c6  xor     rcx, rsp; StackCookie
0x1800157c9  call    __security_check_cookie
0x1800157ce  lea     r11, [rsp+870h+var_s0]
0x1800157d6  mov     rbx, [r11+18h]
0x1800157da  mov     rsi, [r11+20h]
0x1800157de  mov     rsp, r11
0x1800157e1  pop     rbp
0x1800157e2  retn
```
