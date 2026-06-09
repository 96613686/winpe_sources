# CNamespaceManagement::UpdateQuery(ushort const *,ulong)

- ea: `0x18001947c`
- end: `0x180019519`
- name: `?UpdateQuery@CNamespaceManagement@@QEAAJPEBGK@Z`
- size: `157`
- prototype: `__int64 __fastcall(CNamespaceManagement *__hidden this, STRSAFE_PCNZWCH pszSrc, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000e230`

## callees

- `0x1800021f0`
- `0x180003b08`
- `0x1800079f0`
- `0x180017648`
- `0x18001947c`

## pseudocode

```c
__int64 __fastcall CNamespaceManagement::UpdateQuery(
        CNamespaceManagement *this,
        STRSAFE_PCNZWCH pszSrc,
        unsigned int a3)
{
  int v6; // edi
  STRSAFE_PCNZWCH pszSrca; // [rsp+48h] [rbp+20h] BYREF

  CAutoWChar::CAutoWChar((CAutoWChar *)&pszSrca, 260);
  if ( pszSrca )
  {
    v6 = CNamespaceManagement::AddToQuery(this, pszSrc);
    if ( v6 >= 0 )
    {
      v6 = StringCchPrintfW((unsigned __int16 *)pszSrca, 0x104u, L"%lu", a3);
      if ( v6 >= 0 )
      {
        v6 = CNamespaceManagement::AddToQuery(this, pszSrca);
        if ( v6 >= 0 )
          *((_DWORD *)this + 20) = 0;
      }
    }
  }
  else
  {
    v6 = -2147217402;
  }
  CAutoWChar::~CAutoWChar((void **)&pszSrca);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001947c  mov     [rsp+arg_0], rbp
0x180019481  mov     [rsp+arg_8], rsi
0x180019486  push    rdi
0x180019487  sub     rsp, 20h
0x18001948b  mov     ebp, r8d
0x18001948e  mov     rdi, rdx
0x180019491  mov     rsi, rcx
0x180019494  mov     edx, 104h; int
0x180019499  lea     rcx, [rsp+28h+pszSrc]; this
0x18001949e  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x1800194a3  nop
0x1800194a4  cmp     [rsp+28h+pszSrc], 0
0x1800194aa  jnz     short loc_1800194B3
0x1800194ac  mov     edi, 80041006h
0x1800194b1  jmp     short loc_1800194FD
0x1800194b3  mov     rdx, rdi; pszSrc
0x1800194b6  mov     rcx, rsi; this
0x1800194b9  call    ?AddToQuery@CNamespaceManagement@@QEAAJPEBG@Z; CNamespaceManagement::AddToQuery(ushort const *)
0x1800194be  mov     edi, eax
0x1800194c0  test    eax, eax
0x1800194c2  js      short loc_1800194FD
0x1800194c4  mov     r9d, ebp
0x1800194c7  lea     r8, aLu; "%lu"
0x1800194ce  mov     edx, 104h; unsigned __int64
0x1800194d3  mov     rcx, [rsp+28h+pszSrc]; unsigned __int16 *
0x1800194d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800194dd  mov     edi, eax
0x1800194df  test    eax, eax
0x1800194e1  js      short loc_1800194FD
0x1800194e3  mov     rdx, [rsp+28h+pszSrc]; pszSrc
0x1800194e8  mov     rcx, rsi; this
0x1800194eb  call    ?AddToQuery@CNamespaceManagement@@QEAAJPEBG@Z; CNamespaceManagement::AddToQuery(ushort const *)
0x1800194f0  mov     edi, eax
0x1800194f2  test    eax, eax
0x1800194f4  js      short loc_1800194FD
0x1800194f6  mov     dword ptr [rsi+50h], 0
0x1800194fd  lea     rcx, [rsp+28h+pszSrc]; this
0x180019502  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x180019507  mov     eax, edi
0x180019509  mov     rbp, [rsp+28h+arg_0]
0x18001950e  mov     rsi, [rsp+28h+arg_8]
0x180019513  add     rsp, 20h
0x180019517  pop     rdi
0x180019518  retn
```
