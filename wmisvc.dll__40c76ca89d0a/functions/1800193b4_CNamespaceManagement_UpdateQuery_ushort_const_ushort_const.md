# CNamespaceManagement::UpdateQuery(ushort const *,ushort const *)

- ea: `0x1800193b4`
- end: `0x180019476`
- name: `?UpdateQuery@CNamespaceManagement@@QEAAJPEBG0@Z`
- size: `194`
- prototype: `__int64 __fastcall(CNamespaceManagement *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000e230`
- `0x180017e3c`

## callees

- `0x1800021f0`
- `0x1800031e0`
- `0x1800079f0`
- `0x180017648`
- `0x1800193b4`

## pseudocode

```c
__int64 __fastcall CNamespaceManagement::UpdateQuery(
        CNamespaceManagement *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v5; // edi
  STRSAFE_PCNZWCH pszSrc; // [rsp+38h] [rbp+10h] BYREF

  pszSrc = a2;
  CAutoWChar::CAutoWChar((CAutoWChar *)&pszSrc, 780);
  if ( pszSrc )
  {
    v5 = ConvertStringToCTypeString((unsigned __int16 *)pszSrc, 780, a3);
    if ( v5 >= 0 )
    {
      if ( *((_DWORD *)this + 20) || (v5 = CNamespaceManagement::AddToQuery(this, &qword_180025A78), v5 >= 0) )
      {
        v5 = CNamespaceManagement::AddToQuery(this, L"\"");
        if ( v5 >= 0 )
        {
          v5 = CNamespaceManagement::AddToQuery(this, pszSrc);
          if ( v5 >= 0 )
          {
            v5 = CNamespaceManagement::AddToQuery(this, L"\"");
            if ( v5 >= 0 )
              *((_DWORD *)this + 20) = 0;
          }
        }
      }
    }
  }
  else
  {
    v5 = -2147217402;
  }
  CAutoWChar::~CAutoWChar((void **)&pszSrc);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800193b4  mov     [rsp+arg_0], rsi
0x1800193b9  mov     [rsp+pszSrc], rdx
0x1800193be  push    rdi
0x1800193bf  sub     rsp, 20h
0x1800193c3  mov     rdi, r8
0x1800193c6  mov     rsi, rcx
0x1800193c9  mov     edx, 30Ch; int
0x1800193ce  lea     rcx, [rsp+28h+pszSrc]; this
0x1800193d3  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x1800193d8  nop
0x1800193d9  cmp     [rsp+28h+pszSrc], 0
0x1800193df  jnz     short loc_1800193E8
0x1800193e1  mov     edi, 80041006h
0x1800193e6  jmp     short loc_18001945F
0x1800193e8  mov     r8, rdi; unsigned __int16 *
0x1800193eb  mov     edx, 30Ch; int
0x1800193f0  mov     rcx, [rsp+28h+pszSrc]; unsigned __int16 *
0x1800193f5  call    ?ConvertStringToCTypeString@@YAJPEAGHPEBG@Z; ConvertStringToCTypeString(ushort *,int,ushort const *)
0x1800193fa  mov     edi, eax
0x1800193fc  test    eax, eax
0x1800193fe  js      short loc_18001945F
0x180019400  cmp     dword ptr [rsi+50h], 0
0x180019404  jnz     short loc_18001941B
0x180019406  lea     rdx, qword_180025A78; pszSrc
0x18001940d  mov     rcx, rsi; this
0x180019410  call    ?AddToQuery@CNamespaceManagement@@QEAAJPEBG@Z; CNamespaceManagement::AddToQuery(ushort const *)
0x180019415  mov     edi, eax
0x180019417  test    eax, eax
0x180019419  js      short loc_18001945F
0x18001941b  lea     rdx, asc_180026110; "\""
0x180019422  mov     rcx, rsi; this
0x180019425  call    ?AddToQuery@CNamespaceManagement@@QEAAJPEBG@Z; CNamespaceManagement::AddToQuery(ushort const *)
0x18001942a  mov     edi, eax
0x18001942c  test    eax, eax
0x18001942e  js      short loc_18001945F
0x180019430  mov     rdx, [rsp+28h+pszSrc]; pszSrc
0x180019435  mov     rcx, rsi; this
0x180019438  call    ?AddToQuery@CNamespaceManagement@@QEAAJPEBG@Z; CNamespaceManagement::AddToQuery(ushort const *)
0x18001943d  mov     edi, eax
0x18001943f  test    eax, eax
0x180019441  js      short loc_18001945F
0x180019443  lea     rdx, asc_180026110; "\""
0x18001944a  mov     rcx, rsi; this
0x18001944d  call    ?AddToQuery@CNamespaceManagement@@QEAAJPEBG@Z; CNamespaceManagement::AddToQuery(ushort const *)
0x180019452  mov     edi, eax
0x180019454  test    eax, eax
0x180019456  js      short loc_18001945F
0x180019458  mov     dword ptr [rsi+50h], 0
0x18001945f  lea     rcx, [rsp+28h+pszSrc]; this
0x180019464  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x180019469  mov     eax, edi
0x18001946b  mov     rsi, [rsp+28h+arg_0]
0x180019470  add     rsp, 20h
0x180019474  pop     rdi
0x180019475  retn
```
