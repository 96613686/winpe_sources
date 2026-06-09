# DAV_PROPERTY_STORE_MANAGER::LoadAndInitializeStore(INativeConfigurationElement *,INativeConfigurationElementCollection *)

- ea: `0x180005184`
- end: `0x18000532d`
- name: `?LoadAndInitializeStore@DAV_PROPERTY_STORE_MANAGER@@AEAAJPEAVINativeConfigurationElement@@PEAVINativeConfigurationElementCollection@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(DAV_PROPERTY_STORE_MANAGER *__hidden this, struct INativeConfigurationElement *, struct INativeConfigurationElementCollection *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180004e20`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x1800043b0`
- `0x180004808`
- `0x180004c58`
- `0x180004f9c`
- `0x180005184`
- `0x18001bf60`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180005272`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000527c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005272`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000527c`

## string_xrefs

- `0x1800051f3`: `xmlNamespace`

## pseudocode

```c
__int64 __fastcall DAV_PROPERTY_STORE_MANAGER::LoadAndInitializeStore(
        DAV_PROPERTY_STORE_MANAGER *this,
        struct INativeConfigurationElement *a2,
        struct INativeConfigurationElementCollection *a3)
{
  __int64 v3; // rax
  struct INativeConfigurationElement *v7; // rsi
  int CollectionElement; // edi
  int v9; // r8d
  const unsigned __int16 *v10; // rdx
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v15; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v16; // [rsp+78h] [rbp+38h] BYREF
  struct INativeConfigurationElement *v17; // [rsp+88h] [rbp+48h] BYREF

  v3 = *(_QWORD *)a2;
  v17 = 0;
  v16 = 0;
  v15 = 0;
  v7 = 0;
  CollectionElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(v3 + 64))(
                        a2,
                        L"propertyStore",
                        &v15,
                        0,
                        0);
  if ( CollectionElement < 0 )
    return (unsigned int)CollectionElement;
  CollectionElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
                        a2,
                        L"xmlNamespace",
                        &v16,
                        0,
                        0);
  if ( CollectionElement < 0 )
    return (unsigned int)CollectionElement;
  if ( *v16 != 42 || v16[1] )
  {
    CollectionElement = 0;
  }
  else
  {
    if ( STATIC_WSTRING_HASH::FindKey(this, v16, v9) )
      return 0;
    CollectionElement = FindCollectionElement(a3, v10, v15, &v17);
    if ( CollectionElement >= 0 )
    {
      v11 = operator new(0x98u);
      v12 = v11;
      if ( v11 )
      {
        STRU::STRU((STRU *)(v11 + 4));
        STRU::STRU((STRU *)(v12 + 11));
        v7 = v17;
        *v12 = 0;
        v12[3] = 0;
        v12[18] = 0;
        CollectionElement = DAV_PROPERTY_STORE::LoadAndInitialize((DAV_PROPERTY_STORE *)v12, v15, v16, v7, a2);
        if ( CollectionElement < 0 )
        {
          DAV_PROPERTY_STORE::~DAV_PROPERTY_STORE((DAV_PROPERTY_STORE *)v12);
          operator delete(v12);
        }
        else
        {
          STATIC_WSTRING_HASH::InsertRecord(this, (struct STATIC_WSTRING_HASH_RECORD *)v12);
          v13 = v16;
          ++*((_DWORD *)this + 268);
          if ( *v13 == 42 && !v13[1] )
            *((_QWORD *)this + 132) = v12;
        }
        goto LABEL_17;
      }
      CollectionElement = -2147024888;
    }
    v7 = v17;
  }
LABEL_17:
  if ( v7 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)CollectionElement;
}

```

## disassembly

```asm
0x180005184  mov     [rsp-28h+arg_0], rbx
0x180005189  mov     [rsp-28h+arg_10], rsi
0x18000518e  push    rbp
0x18000518f  push    rdi
0x180005190  push    r12
0x180005192  push    r14
0x180005194  push    r15
0x180005196  mov     rbp, rsp
0x180005199  sub     rsp, 40h
0x18000519d  mov     rax, [rdx]
0x1800051a0  xor     r12d, r12d
0x1800051a3  mov     r15, rdx
0x1800051a6  mov     [rbp+arg_18], r12
0x1800051aa  mov     rbx, r8
0x1800051ad  mov     [rbp+arg_8], r12
0x1800051b1  mov     r14, rcx
0x1800051b4  mov     [rbp+var_10], r12
0x1800051b8  mov     rax, [rax+40h]
0x1800051bc  lea     r8, [rbp+var_10]
0x1800051c0  xor     r9d, r9d
0x1800051c3  mov     [rsp+40h+var_20], r12
0x1800051c8  lea     rdx, aPropertystore; "propertyStore"
0x1800051cf  mov     rcx, r15
0x1800051d2  mov     esi, r12d
0x1800051d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051da  mov     edi, eax
0x1800051dc  test    eax, eax
0x1800051de  js      loc_180005312
0x1800051e4  mov     rax, [r15]
0x1800051e7  lea     r8, [rbp+arg_8]
0x1800051eb  xor     r9d, r9d
0x1800051ee  mov     [rsp+40h+var_20], r12
0x1800051f3  lea     rdx, aXmlnamespace; "xmlNamespace"
0x1800051fa  mov     rcx, r15
0x1800051fd  mov     rax, [rax+40h]
0x180005201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005206  mov     edi, eax
0x180005208  test    eax, eax
0x18000520a  js      loc_180005312
0x180005210  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x180005214  cmp     word ptr [rdx], 2Ah ; '*'
0x180005218  jnz     loc_1800052FB
0x18000521e  cmp     [rdx+2], r12w
0x180005223  jnz     loc_1800052FB
0x180005229  mov     rcx, r14; this
0x18000522c  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180005231  test    rax, rax
0x180005234  jz      short loc_18000523E
0x180005236  mov     edi, r12d
0x180005239  jmp     loc_180005312
0x18000523e  mov     r8, [rbp+var_10]; unsigned __int16 *
0x180005242  lea     r9, [rbp+arg_18]; struct INativeConfigurationElement **
0x180005246  mov     rcx, rbx; struct INativeConfigurationElementCollection *
0x180005249  call    ?FindCollectionElement@@YAJPEAVINativeConfigurationElementCollection@@PEBG1PEAPEAVINativeConfigurationElement@@@Z; FindCollectionElement(INativeConfigurationElementCollection *,ushort const *,ushort const *,INativeConfigurationElement * *)
0x18000524e  mov     edi, eax
0x180005250  test    eax, eax
0x180005252  js      loc_1800052F5
0x180005258  mov     ecx, 98h; Size
0x18000525d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005262  mov     rbx, rax
0x180005265  test    rax, rax
0x180005268  jz      loc_1800052F0
0x18000526e  lea     rcx, [rax+20h]
0x180005272  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005278  lea     rcx, [rbx+58h]
0x18000527c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005282  mov     rsi, [rbp+arg_18]
0x180005286  mov     rcx, rbx; this
0x180005289  mov     [rbx], r12
0x18000528c  mov     r9, rsi; struct INativeConfigurationElement *
0x18000528f  mov     [rbx+18h], r12
0x180005293  mov     [rbx+90h], r12
0x18000529a  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x18000529e  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x1800052a2  mov     [rsp+40h+var_20], r15; struct INativeConfigurationElement *
0x1800052a7  call    ?LoadAndInitialize@DAV_PROPERTY_STORE@@QEAAJPEBG0PEAVINativeConfigurationElement@@1@Z; DAV_PROPERTY_STORE::LoadAndInitialize(ushort const *,ushort const *,INativeConfigurationElement *,INativeConfigurationElement *)
0x1800052ac  mov     edi, eax
0x1800052ae  test    eax, eax
0x1800052b0  js      short loc_1800052DE
0x1800052b2  mov     rdx, rbx; struct STATIC_WSTRING_HASH_RECORD *
0x1800052b5  mov     rcx, r14; this
0x1800052b8  call    ?InsertRecord@STATIC_WSTRING_HASH@@QEAAXPEAUSTATIC_WSTRING_HASH_RECORD@@@Z; STATIC_WSTRING_HASH::InsertRecord(STATIC_WSTRING_HASH_RECORD *)
0x1800052bd  mov     rax, [rbp+arg_8]
0x1800052c1  inc     dword ptr [r14+430h]
0x1800052c8  cmp     word ptr [rax], 2Ah ; '*'
0x1800052cc  jnz     short loc_1800052FE
0x1800052ce  cmp     [rax+2], r12w
0x1800052d3  jnz     short loc_1800052FE
0x1800052d5  mov     [r14+420h], rbx
0x1800052dc  jmp     short loc_1800052FE
0x1800052de  mov     rcx, rbx; this
0x1800052e1  call    ??1DAV_PROPERTY_STORE@@QEAA@XZ; DAV_PROPERTY_STORE::~DAV_PROPERTY_STORE(void)
0x1800052e6  mov     rcx, rbx; Block
0x1800052e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800052ee  jmp     short loc_1800052FE
0x1800052f0  mov     edi, 80070008h
0x1800052f5  mov     rsi, [rbp+arg_18]
0x1800052f9  jmp     short loc_1800052FE
0x1800052fb  mov     edi, r12d
0x1800052fe  test    rsi, rsi
0x180005301  jz      short loc_180005312
0x180005303  mov     rax, [rsi]
0x180005306  mov     rcx, rsi
0x180005309  mov     rax, [rax+10h]
0x18000530d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005312  lea     r11, [rsp+40h+var_s0]
0x180005317  mov     eax, edi
0x180005319  mov     rbx, [r11+30h]
0x18000531d  mov     rsi, [r11+40h]
0x180005321  mov     rsp, r11
0x180005324  pop     r15
0x180005326  pop     r14
0x180005328  pop     r12
0x18000532a  pop     rdi
0x18000532b  pop     rbp
0x18000532c  retn
```
