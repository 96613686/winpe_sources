# CDavSetParser::HandleNewProperty(IXmlReader *,ushort const *,ushort const *)

- ea: `0x180012774`
- end: `0x18001291c`
- name: `?HandleNewProperty@CDavSetParser@@AEAAJPEAUIXmlReader@@PEBG1@Z`
- size: `424`
- prototype: `__int64 __fastcall(CDavSetParser *__hidden this, struct IXmlReader *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180012970`

## callees

- `0x180004534`
- `0x1800122e0`
- `0x180012614`
- `0x180012774`
- `0x18001e898`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001281c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001283e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001289c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001281c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001283e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001289c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012853`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012853`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800128b1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800128b1`

## pseudocode

```c
__int64 __fastcall CDavSetParser::HandleNewProperty(
        CDavSetParser *this,
        struct IXmlReader *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int LanguageTag; // ebx
  char *v9; // r13
  _WORD *v10; // rcx
  _WORD *v11; // rcx
  _WORD *v12; // rcx
  _WORD *v13; // rcx
  const unsigned __int16 *v14; // rsi
  int v16; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v17[32]; // [rsp+28h] [rbp-90h] BYREF
  const unsigned __int16 *v18; // [rsp+48h] [rbp-70h]

  LanguageTag = 0;
  **((_WORD **)this + 8) = 0;
  v9 = (char *)this + 144;
  v10 = (_WORD *)*((_QWORD *)this + 15);
  *((_DWORD *)this + 20) = 0;
  *v10 = 0;
  v11 = (_WORD *)*((_QWORD *)v9 + 4);
  *((_DWORD *)this + 34) = 0;
  *v11 = 0;
  v12 = (_WORD *)*((_QWORD *)this + 29);
  *((_DWORD *)v9 + 12) = 0;
  *v12 = 0;
  v13 = (_WORD *)*((_QWORD *)this + 36);
  *((_DWORD *)this + 62) = 0;
  *v13 = 0;
  *((_DWORD *)this + 76) = 0;
  DAV_NAMESPACE_SET::Flush((CDavSetParser *)((char *)this + 312));
  *(_QWORD *)((char *)this + 20) = 0;
  *((_DWORD *)this + 4) = 0;
  if ( !*a3 || (LanguageTag = STRU::Copy((CDavSetParser *)((char *)this + 88), a3), LanguageTag >= 0) )
  {
    if ( *a4 )
      LanguageTag = STRU::Copy((CDavSetParser *)((char *)this + 32), a4);
    if ( LanguageTag >= 0 )
    {
      STRU::STRU((STRU *)v17);
      v14 = (const unsigned __int16 *)*((_QWORD *)this + 725);
      v16 = 0;
      LanguageTag = XmlFindLanguageTag(a2, (struct STRU *)v17, &v16);
      if ( LanguageTag >= 0 )
      {
        if ( v16 )
          v14 = v18;
        if ( v14 )
        {
          if ( *v14 )
          {
            LanguageTag = STRU::Copy((STRU *)v9, v14);
            if ( LanguageTag >= 0 )
              *((_DWORD *)this + 5) = 1;
          }
        }
      }
      STRU::~STRU((STRU *)v17);
      if ( LanguageTag >= 0 )
      {
        LanguageTag = CDavSetParser::AppendOtherAttributes(this, a2, (CDavSetParser *)((char *)this + 256), 1);
        if ( LanguageTag >= 0 )
        {
          if ( ((unsigned int (__fastcall *)(struct IXmlReader *))a2->lpVtbl->IsEmptyElement)(a2) )
            return (unsigned int)CDavSetParser::FinalizeProperty(this);
          else
            ++*((_DWORD *)this + 4);
        }
      }
    }
  }
  return (unsigned int)LanguageTag;
}

```

## disassembly

```asm
0x180012774  push    rbx
0x180012776  push    rbp
0x180012777  push    rsi
0x180012778  push    rdi
0x180012779  push    r12
0x18001277b  push    r13
0x18001277d  push    r14
0x18001277f  push    r15
0x180012781  sub     rsp, 78h
0x180012785  mov     rax, cs:__security_cookie
0x18001278c  xor     rax, rsp
0x18001278f  mov     [rsp+0B8h+var_58], rax
0x180012794  mov     rdi, rcx
0x180012797  mov     r12, r8
0x18001279a  mov     rcx, [rcx+40h]
0x18001279e  xor     r8d, r8d
0x1800127a1  mov     r14, rdx
0x1800127a4  mov     rsi, r9
0x1800127a7  mov     ebx, r8d
0x1800127aa  lea     rdx, [rdi+100h]
0x1800127b1  mov     [rcx], r8w
0x1800127b5  lea     r13, [rdi+90h]
0x1800127bc  mov     rcx, [rdi+78h]
0x1800127c0  mov     [rdi+50h], r8d
0x1800127c4  mov     [rcx], r8w
0x1800127c8  mov     rcx, [r13+20h]
0x1800127cc  mov     [rdi+88h], r8d
0x1800127d3  mov     [rcx], r8w
0x1800127d7  mov     rcx, [rdi+0E8h]
0x1800127de  mov     [r13+30h], r8d
0x1800127e2  mov     [rcx], r8w
0x1800127e6  mov     rcx, [rdx+20h]
0x1800127ea  mov     [rdi+0F8h], r8d
0x1800127f1  mov     [rcx], r8w
0x1800127f5  lea     rcx, [rdi+138h]; this
0x1800127fc  mov     [rdx+30h], r8d
0x180012800  call    ?Flush@DAV_NAMESPACE_SET@@QEAAXXZ; DAV_NAMESPACE_SET::Flush(void)
0x180012805  xor     eax, eax
0x180012807  mov     [rdi+14h], rax
0x18001280b  mov     [rdi+10h], eax
0x18001280e  cmp     [r12], ax
0x180012813  jz      short loc_180012830
0x180012815  mov     rdx, r12
0x180012818  lea     rcx, [rdi+58h]
0x18001281c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012822  xor     ebp, ebp
0x180012824  mov     ebx, eax
0x180012826  test    eax, eax
0x180012828  js      loc_1800128FC
0x18001282e  jmp     short loc_180012832
0x180012830  xor     ebp, ebp
0x180012832  cmp     [rsi], bp
0x180012835  jz      short loc_180012846
0x180012837  mov     rdx, rsi
0x18001283a  lea     rcx, [rdi+20h]
0x18001283e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012844  mov     ebx, eax
0x180012846  test    ebx, ebx
0x180012848  js      loc_1800128FC
0x18001284e  lea     rcx, [rsp+0B8h+var_90]
0x180012853  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012859  mov     rsi, [rdi+16A8h]
0x180012860  lea     r8, [rsp+0B8h+var_98]; int *
0x180012865  lea     rdx, [rsp+0B8h+var_90]; struct STRU *
0x18001286a  mov     [rsp+0B8h+var_98], ebp
0x18001286e  mov     rcx, r14; struct IXmlReader *
0x180012871  call    ?XmlFindLanguageTag@@YAJPEAUIXmlReader@@PEAVSTRU@@PEAH@Z; XmlFindLanguageTag(IXmlReader *,STRU *,int *)
0x180012876  mov     ebx, eax
0x180012878  mov     r15d, 1
0x18001287e  test    eax, eax
0x180012880  js      short loc_1800128AC
0x180012882  cmp     [rsp+0B8h+var_98], ebp
0x180012886  cmovnz  rsi, [rsp+0B8h+var_70]
0x18001288c  test    rsi, rsi
0x18001288f  jz      short loc_1800128AC
0x180012891  cmp     [rsi], bp
0x180012894  jz      short loc_1800128AC
0x180012896  mov     rdx, rsi
0x180012899  mov     rcx, r13
0x18001289c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800128a2  mov     ebx, eax
0x1800128a4  test    eax, eax
0x1800128a6  js      short loc_1800128AC
0x1800128a8  mov     [rdi+14h], r15d
0x1800128ac  lea     rcx, [rsp+0B8h+var_90]
0x1800128b1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800128b7  test    ebx, ebx
0x1800128b9  js      short loc_1800128FC
0x1800128bb  mov     r9d, r15d; int
0x1800128be  lea     r8, [rdi+100h]; struct STRU *
0x1800128c5  mov     rdx, r14; struct IXmlReader *
0x1800128c8  mov     rcx, rdi; this
0x1800128cb  call    ?AppendOtherAttributes@CDavSetParser@@AEAAJPEAUIXmlReader@@PEAVSTRU@@H@Z; CDavSetParser::AppendOtherAttributes(IXmlReader *,STRU *,int)
0x1800128d0  mov     ebx, eax
0x1800128d2  test    eax, eax
0x1800128d4  js      short loc_1800128FC
0x1800128d6  mov     rax, [r14]
0x1800128d9  mov     rcx, r14
0x1800128dc  mov     rax, [rax+0A0h]
0x1800128e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128e8  test    eax, eax
0x1800128ea  jz      short loc_1800128F8
0x1800128ec  mov     rcx, rdi; this
0x1800128ef  call    ?FinalizeProperty@CDavSetParser@@AEAAJXZ; CDavSetParser::FinalizeProperty(void)
0x1800128f4  mov     ebx, eax
0x1800128f6  jmp     short loc_1800128FC
0x1800128f8  add     [rdi+10h], r15d
0x1800128fc  mov     eax, ebx
0x1800128fe  mov     rcx, [rsp+0B8h+var_58]
0x180012903  xor     rcx, rsp; StackCookie
0x180012906  call    __security_check_cookie
0x18001290b  add     rsp, 78h
0x18001290f  pop     r15
0x180012911  pop     r14
0x180012913  pop     r13
0x180012915  pop     r12
0x180012917  pop     rdi
0x180012918  pop     rsi
0x180012919  pop     rbp
0x18001291a  pop     rbx
0x18001291b  retn
```
