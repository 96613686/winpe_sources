# CStringUserSetting::DeserializeString(ushort * *,int)

- ea: `0x180004fe0`
- end: `0x18000512e`
- name: `?DeserializeString@CStringUserSetting@@IEAAJPEAPEAGH@Z`
- size: `334`
- prototype: `__int64 __fastcall(CStringUserSetting *__hidden this, unsigned __int16 **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800057a0`

## callees

- `0x180004eb0`
- `0x180004fe0`
- `0x1800059d8`
- `0x18000892c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18000508a`
- `KERNEL32!GlobalAlloc` at `0x18000508a`
- `WDSCORE!CurrentIP` at `0x180005016`
- `WDSCORE!CurrentIP` at `0x18000509e`
- `WDSCORE!CurrentIP` at `0x1800050df`
- `WDSCORE!CurrentIP` at `0x180005016`
- `WDSCORE!CurrentIP` at `0x18000509e`
- `WDSCORE!CurrentIP` at `0x1800050df`
- `WDSCORE!WdsFreeData` at `0x180005110`
- `WDSCORE!WdsFreeData` at `0x180005110`

## string_xrefs

- `0x180004ff9`: `CStringUserSetting::DeserializeString`

## pseudocode

```c
__int64 __fastcall CStringUserSetting::DeserializeString(CStringUserSetting *this, unsigned __int16 **a2, int a3)
{
  const unsigned __int16 *v3; // rbx
  void *v7; // rax
  unsigned int v8; // ecx
  const unsigned __int16 *v9; // r9
  signed int v10; // edi
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  unsigned __int16 *v13; // rax
  void *v14; // rax
  unsigned int v15; // ecx
  const unsigned __int16 *v16; // r9
  void *v17; // rax
  unsigned int v18; // ecx
  const unsigned __int16 *v19; // r9
  _OWORD v21[4]; // [rsp+30h] [rbp-48h] BYREF

  v3 = &Src;
  v21[0] = 0;
  if ( !a2 )
  {
    v7 = (void *)CurrentIP();
    Ui_Assert(v8, "pstDest != 0", 0x2E9u, v9, L"CStringUserSetting::DeserializeString", v7);
  }
  v10 = CUserSetting::DeserializeField(this, L"Value", 1, (struct WDS_DATA *)v21, a3);
  if ( v10 >= 0 && *((_QWORD *)&v21[0] + 1) )
    v3 = (const unsigned __int16 *)*((_QWORD *)&v21[0] + 1);
  v11 = -1;
  do
    ++v11;
  while ( v3[v11] );
  v12 = (int)v11 + 1;
  v13 = (unsigned __int16 *)GlobalAlloc(0x40u, 2 * v12);
  *a2 = v13;
  if ( !v13 )
  {
    v14 = (void *)CurrentIP();
    Ui_Assert(v15, "*pstDest != 0", 0x2F3u, v16, L"CStringUserSetting::DeserializeString", v14);
  }
  **a2 = 0;
  if ( (int)StringCchCopyW(*a2, v12, v3) < 0 )
  {
    v17 = (void *)CurrentIP();
    Ui_Assert(v18, "(((HRESULT)(hrT)) >= 0)", 0x2F7u, v19, L"CStringUserSetting::DeserializeString", v17);
  }
  if ( v10 >= 0 )
    WdsFreeData(v21);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180004fe0  push    rbx
0x180004fe2  push    rbp
0x180004fe3  push    rsi
0x180004fe4  push    rdi
0x180004fe5  push    r12
0x180004fe7  push    r14
0x180004fe9  push    r15
0x180004feb  sub     rsp, 40h
0x180004fef  xor     r15d, r15d
0x180004ff2  lea     rbx, Src
0x180004ff9  lea     r12, aCstringuserset_1; "CStringUserSetting::DeserializeString"
0x180005000  xorps   xmm0, xmm0
0x180005003  mov     edi, r8d
0x180005006  mov     rsi, rdx
0x180005009  mov     rbp, rcx
0x18000500c  movups  [rsp+78h+var_48], xmm0
0x180005011  test    rdx, rdx
0x180005014  jnz     short loc_18000503E
0x180005016  call    cs:__imp_CurrentIP
0x18000501d  nop     dword ptr [rax+rax+00h]
0x180005022  mov     [rsp+78h+var_50], rax; void *
0x180005027  mov     r8d, 2E9h; unsigned int
0x18000502d  lea     rdx, aPstdest0; "pstDest != 0"
0x180005034  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x180005039  call    ?Ui_Assert@@YAXKPEBDKPEBG1PEAX@Z; Ui_Assert(ulong,char const *,ulong,ushort const *,ushort const *,void *)
0x18000503e  lea     r9, [rsp+78h+var_48]; struct WDS_DATA *
0x180005043  mov     dword ptr [rsp+78h+var_58], edi; int
0x180005047  mov     r8d, 1; unsigned int
0x18000504d  lea     rdx, aValue; "Value"
0x180005054  mov     rcx, rbp; this
0x180005057  call    ?DeserializeField@CUserSetting@@IEAAJPEBGIPEAUWDS_DATA@@H@Z; CUserSetting::DeserializeField(ushort const *,uint,WDS_DATA *,int)
0x18000505c  mov     edi, eax
0x18000505e  test    eax, eax
0x180005060  js      short loc_18000506E
0x180005062  mov     rcx, qword ptr [rsp+78h+var_48+8]
0x180005067  test    rcx, rcx
0x18000506a  cmovnz  rbx, rcx
0x18000506e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005072  inc     rax
0x180005075  cmp     [rbx+rax*2], r15w
0x18000507a  jnz     short loc_180005072
0x18000507c  inc     eax
0x18000507e  mov     ecx, 40h ; '@'; uFlags
0x180005083  movsxd  r14, eax
0x180005086  lea     rdx, [r14+r14]; dwBytes
0x18000508a  call    cs:__imp_GlobalAlloc
0x180005091  nop     dword ptr [rax+rax+00h]
0x180005096  mov     [rsi], rax
0x180005099  test    rax, rax
0x18000509c  jnz     short loc_1800050C6
0x18000509e  call    cs:__imp_CurrentIP
0x1800050a5  nop     dword ptr [rax+rax+00h]
0x1800050aa  mov     [rsp+78h+var_50], rax; void *
0x1800050af  mov     r8d, 2F3h; unsigned int
0x1800050b5  lea     rdx, aPstdest0_0; "*pstDest != 0"
0x1800050bc  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x1800050c1  call    ?Ui_Assert@@YAXKPEBDKPEBG1PEAX@Z; Ui_Assert(ulong,char const *,ulong,ushort const *,ushort const *,void *)
0x1800050c6  mov     rcx, [rsi]
0x1800050c9  mov     r8, rbx; unsigned __int16 *
0x1800050cc  mov     rdx, r14; unsigned __int64
0x1800050cf  mov     [rcx], r15w
0x1800050d3  mov     rcx, [rsi]; unsigned __int16 *
0x1800050d6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800050db  test    eax, eax
0x1800050dd  jns     short loc_180005107
0x1800050df  call    cs:__imp_CurrentIP
0x1800050e6  nop     dword ptr [rax+rax+00h]
0x1800050eb  mov     [rsp+78h+var_50], rax; void *
0x1800050f0  mov     r8d, 2F7h; unsigned int
0x1800050f6  lea     rdx, aHresultHrt0; "(((HRESULT)(hrT)) >= 0)"
0x1800050fd  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x180005102  call    ?Ui_Assert@@YAXKPEBDKPEBG1PEAX@Z; Ui_Assert(ulong,char const *,ulong,ushort const *,ushort const *,void *)
0x180005107  test    edi, edi
0x180005109  js      short loc_18000511C
0x18000510b  lea     rcx, [rsp+78h+var_48]
0x180005110  call    cs:__imp_WdsFreeData
0x180005117  nop     dword ptr [rax+rax+00h]
0x18000511c  mov     eax, edi
0x18000511e  add     rsp, 40h
0x180005122  pop     r15
0x180005124  pop     r14
0x180005126  pop     r12
0x180005128  pop     rdi
0x180005129  pop     rsi
0x18000512a  pop     rbp
0x18000512b  pop     rbx
0x18000512c  retn
```
