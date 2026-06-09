# ParseOwnerSubElement(IXmlReader *,ushort const *,STRU *)

- ea: `0x18001317c`
- end: `0x18001324b`
- name: `?ParseOwnerSubElement@@YAJPEAUIXmlReader@@PEBGPEAVSTRU@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(struct IXmlReader *, const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001307c`

## callees

- `0x180008a1c`
- `0x1800120e0`
- `0x18001317c`
- `0x180013a48`
- `0x18001e290`
- `0x180022520`
- `0x1800225b0`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800131f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800131fe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001320c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013217`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013222`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800131f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800131fe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001320c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013217`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013222`

## pseudocode

```c
__int64 __fastcall ParseOwnerSubElement(struct IXmlReader *a1, const unsigned __int16 *a2, struct STRU *a3)
{
  int v5; // r8d
  int v6; // ebx
  _BYTE v8[8]; // [rsp+20h] [rbp-16C8h] BYREF
  int v9; // [rsp+28h] [rbp-16C0h]
  _BYTE v10[56]; // [rsp+40h] [rbp-16A8h] BYREF
  _BYTE v11[56]; // [rsp+78h] [rbp-1670h] BYREF
  _BYTE v12[56]; // [rsp+B0h] [rbp-1638h] BYREF
  _BYTE v13[56]; // [rsp+E8h] [rbp-1600h] BYREF
  _BYTE v14[56]; // [rsp+120h] [rbp-15C8h] BYREF
  _BYTE v15[5496]; // [rsp+158h] [rbp-1590h] BYREF

  CDavSetParser::CDavSetParser((CDavSetParser *)v8, a2);
  v6 = XmlEnum(a1, (struct IXmlEnumerator *)v8, v5);
  if ( v6 >= 0 )
  {
    v6 = v9;
    if ( v9 >= 0 )
      v6 = CDavSetParser::RenderAsStringAndAppend((CDavSetParser *)v8, a3);
  }
  DAV_NAMESPACE_SET::~DAV_NAMESPACE_SET((DAV_NAMESPACE_SET *)v15);
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v13);
  STRU::~STRU((STRU *)v12);
  STRU::~STRU((STRU *)v11);
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001317c  mov     [rsp+arg_8], rbx
0x180013181  push    rdi
0x180013182  mov     eax, 16E0h
0x180013187  call    _alloca_probe
0x18001318c  sub     rsp, rax
0x18001318f  mov     rax, cs:__security_cookie
0x180013196  xor     rax, rsp
0x180013199  mov     [rsp+16E8h+var_18], rax
0x1800131a1  mov     rbx, rcx
0x1800131a4  mov     rdi, r8
0x1800131a7  lea     rcx, [rsp+16E8h+var_16C8]; this
0x1800131ac  call    ??0CDavSetParser@@QEAA@PEBG@Z; CDavSetParser::CDavSetParser(ushort const *)
0x1800131b1  lea     rdx, [rsp+16E8h+var_16C8]; struct IXmlEnumerator *
0x1800131b6  mov     rcx, rbx; struct IXmlReader *
0x1800131b9  call    ?XmlEnum@@YAJPEAUIXmlReader@@PEAVIXmlEnumerator@@H@Z; XmlEnum(IXmlReader *,IXmlEnumerator *,int)
0x1800131be  mov     ebx, eax
0x1800131c0  test    eax, eax
0x1800131c2  js      short loc_1800131DB
0x1800131c4  mov     ebx, [rsp+16E8h+var_16C0]
0x1800131c8  test    ebx, ebx
0x1800131ca  js      short loc_1800131DB
0x1800131cc  mov     rdx, rdi; struct STRU *
0x1800131cf  lea     rcx, [rsp+16E8h+var_16C8]; this
0x1800131d4  call    ?RenderAsStringAndAppend@CDavSetParser@@QEAAJPEAVSTRU@@@Z; CDavSetParser::RenderAsStringAndAppend(STRU *)
0x1800131d9  mov     ebx, eax
0x1800131db  lea     rcx, [rsp+16E8h+var_1590]; this
0x1800131e3  call    ??1DAV_NAMESPACE_SET@@UEAA@XZ; DAV_NAMESPACE_SET::~DAV_NAMESPACE_SET(void)
0x1800131e8  lea     rcx, [rsp+16E8h+var_15C8]
0x1800131f0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800131f6  lea     rcx, [rsp+16E8h+var_1600]
0x1800131fe  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013204  lea     rcx, [rsp+16E8h+var_1638]
0x18001320c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013212  lea     rcx, [rsp+16E8h+var_1670]
0x180013217  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001321d  lea     rcx, [rsp+16E8h+var_16A8]
0x180013222  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013228  mov     eax, ebx
0x18001322a  mov     rcx, [rsp+16E8h+var_18]
0x180013232  xor     rcx, rsp; StackCookie
0x180013235  call    __security_check_cookie
0x18001323a  mov     rbx, [rsp+16E8h+arg_8]
0x180013242  add     rsp, 16E0h
0x180013249  pop     rdi
0x18001324a  retn
```
