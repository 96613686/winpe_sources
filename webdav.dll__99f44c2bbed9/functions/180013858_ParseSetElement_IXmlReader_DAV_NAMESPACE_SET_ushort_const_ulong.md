# ParseSetElement(IXmlReader *,DAV_NAMESPACE_SET *,ushort const *,ulong)

- ea: `0x180013858`
- end: `0x180013a42`
- name: `?ParseSetElement@@YAJPEAUIXmlReader@@PEAVDAV_NAMESPACE_SET@@PEBGK@Z`
- size: `490`
- prototype: `__int64 __fastcall(struct IXmlReader *, struct DAV_NAMESPACE_SET *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800134f0`

## callees

- `0x180008a1c`
- `0x18000ba90`
- `0x1800120e0`
- `0x180013858`
- `0x18001e290`
- `0x18001e6a4`
- `0x18001e998`
- `0x180022520`
- `0x1800225b0`
- `0x180023010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800139e8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800139f2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800139fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013a06`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013a10`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800139e8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800139f2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800139fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013a06`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013a10`

## pseudocode

```c
__int64 __fastcall ParseSetElement(
        struct IXmlReader *a1,
        struct DAV_NAMESPACE_SET *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int v6; // edi
  int FirstSubElement; // eax
  int v8; // r8d
  bool i; // zf
  int v10; // ebx
  unsigned __int16 *v11; // r15
  unsigned __int16 *v12; // r14
  __int64 v13; // rbx
  __int64 v14; // r12
  __int64 v15; // rdi
  int v16; // eax
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-BCh]
  unsigned __int16 *v20; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+74h] [rbp-8Ch]
  int v25; // [rsp+78h] [rbp-88h]
  _BYTE v26[32]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v27; // [rsp+A0h] [rbp-60h]
  _BYTE v28[32]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v29; // [rsp+D8h] [rbp-28h]
  _BYTE v30[32]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v31; // [rsp+110h] [rbp+10h]
  _BYTE v32[32]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v33; // [rsp+148h] [rbp+48h]
  _BYTE v34[32]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v35; // [rsp+180h] [rbp+80h]
  _BYTE v36[5496]; // [rsp+198h] [rbp+98h] BYREF

  v19 = a4;
  v18 = 0;
  v21[0] = 0;
  v20 = 0;
  v6 = 0;
  CDavSetParser::CDavSetParser((CDavSetParser *)v22, a3);
  FirstSubElement = XmlFindFirstSubElement(a1, &v18, (const unsigned __int16 **)v21, (const unsigned __int16 **)&v20);
  for ( i = FirstSubElement == 1; ; i = FirstSubElement == 1 )
  {
    v10 = FirstSubElement;
    if ( i )
      break;
    if ( FirstSubElement < 0 )
      goto LABEL_13;
    v10 = XmlEnum(a1, (struct IXmlEnumerator *)v22, v8);
    if ( v10 < 0 )
      goto LABEL_13;
    v10 = v23;
    if ( v23 < 0 )
      goto LABEL_13;
    v11 = v29;
    v12 = v27;
    v13 = v31 & -(__int64)(v24 != 0);
    v14 = v33;
    v15 = v35 & -(__int64)(v25 != 0);
    v16 = IsLiveProperty(v29, v27, v19)
        ? (*(__int64 (__fastcall **)(char *, unsigned __int16 *, __int64, __int64, __int64, _QWORD))(*((_QWORD *)a2 + 550) + 32LL))(
            (char *)a2 + 4400,
            v12,
            v14,
            v13,
            v15,
            0)
        : (*(unsigned __int64 (__fastcall **)(struct DAV_NAMESPACE_SET *, unsigned __int16 *, unsigned __int16 *, __int64, __int64, __int64, _QWORD))(*(_QWORD *)a2 + 32LL))(
            a2,
            v11,
            v12,
            v14,
            v13,
            v15,
            0);
    v10 = v16;
    if ( v16 < 0 )
      goto LABEL_13;
    v6 = 1;
    FirstSubElement = XmlFindNextSubElement(a1, v18, (const unsigned __int16 **)v21, (const unsigned __int16 **)&v20);
  }
  v10 = 0;
  if ( !v6 )
    v10 = -2147024809;
LABEL_13:
  DAV_NAMESPACE_SET::~DAV_NAMESPACE_SET((DAV_NAMESPACE_SET *)v36);
  STRU::~STRU((STRU *)v34);
  STRU::~STRU((STRU *)v32);
  STRU::~STRU((STRU *)v30);
  STRU::~STRU((STRU *)v28);
  STRU::~STRU((STRU *)v26);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180013858  mov     [rsp-8+arg_10], rbx
0x18001385d  push    rbp
0x18001385e  push    rsi
0x18001385f  push    rdi
0x180013860  push    r12
0x180013862  push    r13
0x180013864  push    r14
0x180013866  push    r15
0x180013868  lea     rbp, [rsp-1620h]
0x180013870  mov     eax, 1720h
0x180013875  call    _alloca_probe
0x18001387a  sub     rsp, rax
0x18001387d  mov     rax, cs:__security_cookie
0x180013884  xor     rax, rsp
0x180013887  mov     [rbp+1650h+var_40], rax
0x18001388e  mov     r13, rdx
0x180013891  mov     [rsp+1750h+var_170C], r9d
0x180013896  mov     rsi, rcx
0x180013899  mov     [rsp+1750h+var_1710], 0
0x1800138a1  mov     rdx, r8; unsigned __int16 *
0x1800138a4  mov     [rsp+1750h+var_1700], 0
0x1800138ad  lea     rcx, [rsp+1750h+var_16F0]; this
0x1800138b2  mov     [rsp+1750h+var_1708], 0
0x1800138bb  xor     edi, edi
0x1800138bd  call    ??0CDavSetParser@@QEAA@PEBG@Z; CDavSetParser::CDavSetParser(ushort const *)
0x1800138c2  lea     r9, [rsp+1750h+var_1708]; unsigned __int16 **
0x1800138c7  mov     rcx, rsi; struct IXmlReader *
0x1800138ca  lea     r8, [rsp+1750h+var_1700]; unsigned __int16 **
0x1800138cf  lea     rdx, [rsp+1750h+var_1710]; unsigned int *
0x1800138d4  call    ?XmlFindFirstSubElement@@YAJPEAUIXmlReader@@PEAIPEAPEBG2@Z; XmlFindFirstSubElement(IXmlReader *,uint *,ushort const * *,ushort const * *)
0x1800138d9  cmp     eax, 1
0x1800138dc  jmp     loc_1800139C4
0x1800138e1  test    ebx, ebx
0x1800138e3  js      loc_1800139D8
0x1800138e9  lea     rdx, [rsp+1750h+var_16F0]; struct IXmlEnumerator *
0x1800138ee  mov     rcx, rsi; struct IXmlReader *
0x1800138f1  call    ?XmlEnum@@YAJPEAUIXmlReader@@PEAVIXmlEnumerator@@H@Z; XmlEnum(IXmlReader *,IXmlEnumerator *,int)
0x1800138f6  mov     ebx, eax
0x1800138f8  test    eax, eax
0x1800138fa  js      loc_1800139D8
0x180013900  mov     ebx, [rsp+1750h+var_16E8]
0x180013904  test    ebx, ebx
0x180013906  js      loc_1800139D8
0x18001390c  mov     eax, [rsp+1750h+var_16DC]
0x180013910  mov     r15, [rbp+1650h+var_1678]
0x180013914  neg     eax
0x180013916  mov     eax, [rsp+1750h+var_16D8]
0x18001391a  mov     rcx, r15; unsigned __int16 *
0x18001391d  mov     r14, [rbp+1650h+var_16B0]
0x180013921  sbb     rbx, rbx
0x180013924  and     rbx, [rbp+1650h+var_1640]
0x180013928  mov     rdx, r14; unsigned __int16 *
0x18001392b  mov     r8d, [rsp+1750h+var_170C]; unsigned int
0x180013930  neg     eax
0x180013932  mov     r12, [rbp+1650h+var_1608]
0x180013936  sbb     rdi, rdi
0x180013939  and     rdi, [rbp+1650h+var_15D0]
0x180013940  call    ?IsLiveProperty@@YAHPEBG0K@Z; IsLiveProperty(ushort const *,ushort const *,ulong)
0x180013945  test    eax, eax
0x180013947  jz      short loc_180013975
0x180013949  lea     rcx, [r13+1130h]
0x180013950  mov     [rsp+1750h+var_1728], 0
0x180013959  mov     rax, [rcx]
0x18001395c  mov     r9, rbx
0x18001395f  mov     r8, r12
0x180013962  mov     [rsp+1750h+var_1730], rdi
0x180013967  mov     rdx, r14
0x18001396a  mov     rax, [rax+20h]
0x18001396e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013973  jmp     short loc_1800139A1
0x180013975  mov     rax, [r13+0]
0x180013979  mov     r9, r12
0x18001397c  mov     [rsp+1750h+var_1720], 0
0x180013985  mov     r8, r14
0x180013988  mov     [rsp+1750h+var_1728], rdi
0x18001398d  mov     rdx, r15
0x180013990  mov     rcx, r13
0x180013993  mov     [rsp+1750h+var_1730], rbx
0x180013998  mov     rax, [rax+20h]
0x18001399c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139a1  mov     ebx, eax
0x1800139a3  test    eax, eax
0x1800139a5  js      short loc_1800139D8
0x1800139a7  mov     edx, [rsp+1750h+var_1710]; unsigned int
0x1800139ab  lea     r9, [rsp+1750h+var_1708]; unsigned __int16 **
0x1800139b0  lea     r8, [rsp+1750h+var_1700]; unsigned __int16 **
0x1800139b5  mov     rcx, rsi; struct IXmlReader *
0x1800139b8  mov     edi, 1
0x1800139bd  call    ?XmlFindNextSubElement@@YAJPEAUIXmlReader@@IPEAPEBG1@Z; XmlFindNextSubElement(IXmlReader *,uint,ushort const * *,ushort const * *)
0x1800139c2  cmp     eax, edi
0x1800139c4  mov     ebx, eax
0x1800139c6  jnz     loc_1800138E1
0x1800139cc  xor     ebx, ebx
0x1800139ce  mov     eax, 80070057h
0x1800139d3  test    edi, edi
0x1800139d5  cmovz   ebx, eax
0x1800139d8  lea     rcx, [rbp+1650h+var_15B8]; this
0x1800139df  call    ??1DAV_NAMESPACE_SET@@UEAA@XZ; DAV_NAMESPACE_SET::~DAV_NAMESPACE_SET(void)
0x1800139e4  lea     rcx, [rbp+1650h+var_15F0]
0x1800139e8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800139ee  lea     rcx, [rbp+1650h+var_1628]
0x1800139f2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800139f8  lea     rcx, [rbp+1650h+var_1660]
0x1800139fc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013a02  lea     rcx, [rbp+1650h+var_1698]
0x180013a06  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013a0c  lea     rcx, [rbp+1650h+var_16D0]
0x180013a10  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013a16  mov     eax, ebx
0x180013a18  mov     rcx, [rbp+1650h+var_40]
0x180013a1f  xor     rcx, rsp; StackCookie
0x180013a22  call    __security_check_cookie
0x180013a27  mov     rbx, [rsp+1750h+arg_10]
0x180013a2f  add     rsp, 1720h
0x180013a36  pop     r15
0x180013a38  pop     r14
0x180013a3a  pop     r13
0x180013a3c  pop     r12
0x180013a3e  pop     rdi
0x180013a3f  pop     rsi
0x180013a40  pop     rbp
0x180013a41  retn
```
