# IASPolicy::put_ProfileIPFilterTemplateGuid(ushort *)

- ea: `0x180035ee0`
- end: `0x180036009`
- name: `?put_ProfileIPFilterTemplateGuid@IASPolicy@@UEAAJPEAG@Z`
- size: `297`
- prototype: `__int64 __fastcall(IASPolicy *__hidden this, OLECHAR *psz)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18002cd00`
- `0x18002f240`
- `0x180034f44`
- `0x180035ee0`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180035f68`
- `OLEAUT32!__imp_SysAllocString` at `0x180035f68`
- `OLEAUT32!__imp_VariantInit` at `0x180035efa`
- `OLEAUT32!__imp_VariantInit` at `0x180035efa`

## pseudocode

```c
__int64 __fastcall IASPolicy::put_ProfileIPFilterTemplateGuid(IASPolicy *this, OLECHAR *psz)
{
  int ProfileObject; // ebx
  int v5; // edx
  BSTR v6; // rax
  __int64 v7; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  VariantInit(&pvarg);
  if ( *((_QWORD *)this + 16) || (ProfileObject = IASPolicy::GetProfileObject(this), ProfileObject >= 0) )
  {
    pvarg.vt = 8;
    v6 = SysAllocString(psz);
    v7 = *((_QWORD *)this + 16);
    pvarg.llVal = (LONGLONG)v6;
    ProfileObject = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v7 + 72LL))(v7, 1025, &pvarg);
    if ( ProfileObject < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Could not put IP filter GUID property - 0x%x");
      v5 = 50;
      goto LABEL_12;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetProfileObject failed with 0x%x");
    v5 = 49;
LABEL_12:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids,
      (unsigned int)"NPSSDO",
      ProfileObject);
  }
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  return (unsigned int)ProfileObject;
}

```

## disassembly

```asm
0x180035ee0  mov     [rsp+arg_0], rbx
0x180035ee5  mov     [rsp+arg_8], rsi
0x180035eea  push    rdi
0x180035eeb  sub     rsp, 50h
0x180035eef  mov     rdi, rcx
0x180035ef2  mov     rsi, rdx
0x180035ef5  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180035efa  call    cs:__imp_VariantInit
0x180035f00  cmp     qword ptr [rdi+80h], 0
0x180035f08  jnz     short loc_180035F5B
0x180035f0a  mov     rcx, rdi; this
0x180035f0d  call    ?GetProfileObject@IASPolicy@@QEAAJXZ; IASPolicy::GetProfileObject(void)
0x180035f12  mov     ebx, eax
0x180035f14  test    eax, eax
0x180035f16  jns     short loc_180035F5B
0x180035f18  mov     rax, cs:WPP_GLOBAL_Control
0x180035f1f  lea     rcx, WPP_GLOBAL_Control
0x180035f26  cmp     rax, rcx
0x180035f29  jz      loc_180035FED
0x180035f2f  cmp     byte ptr [rax+19h], 2
0x180035f33  jb      loc_180035FED
0x180035f39  test    dword ptr [rax+1Ch], 400h
0x180035f40  jz      loc_180035FED
0x180035f46  mov     edx, ebx
0x180035f48  lea     rcx, aGetprofileobje; "GetProfileObject failed with 0x%x"
0x180035f4f  call    WppDbgPrint
0x180035f54  mov     edx, 31h ; '1'
0x180035f59  jmp     short loc_180035FCB
0x180035f5b  mov     eax, 8
0x180035f60  mov     rcx, rsi; psz
0x180035f63  mov     word ptr [rsp+58h+pvarg], ax
0x180035f68  call    cs:__imp_SysAllocString
0x180035f6e  mov     rcx, [rdi+80h]
0x180035f75  lea     r8, [rsp+58h+pvarg]
0x180035f7a  mov     qword ptr [rsp+58h+pvarg+8], rax
0x180035f7f  mov     edx, 401h
0x180035f84  mov     rax, [rcx]
0x180035f87  mov     rax, [rax+48h]
0x180035f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f90  mov     ebx, eax
0x180035f92  test    eax, eax
0x180035f94  jns     short loc_180035FED
0x180035f96  mov     rax, cs:WPP_GLOBAL_Control
0x180035f9d  lea     rcx, WPP_GLOBAL_Control
0x180035fa4  cmp     rax, rcx
0x180035fa7  jz      short loc_180035FED
0x180035fa9  cmp     byte ptr [rax+19h], 2
0x180035fad  jb      short loc_180035FED
0x180035faf  test    dword ptr [rax+1Ch], 400h
0x180035fb6  jz      short loc_180035FED
0x180035fb8  mov     edx, ebx
0x180035fba  lea     rcx, aCouldNotPutIpF; "Could not put IP filter GUID property -"...
0x180035fc1  call    WppDbgPrint
0x180035fc6  mov     edx, 32h ; '2'
0x180035fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035fd2  lea     r9, aNpssdo; "NPSSDO"
0x180035fd9  lea     r8, WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids
0x180035fe0  mov     [rsp+58h+var_38], ebx
0x180035fe4  mov     rcx, [rcx+10h]
0x180035fe8  call    WPP_SF_sd
0x180035fed  lea     rcx, [rsp+58h+pvarg]; this
0x180035ff2  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180035ff7  mov     rsi, [rsp+58h+arg_8]
0x180035ffc  mov     eax, ebx
0x180035ffe  mov     rbx, [rsp+58h+arg_0]
0x180036003  add     rsp, 50h
0x180036007  pop     rdi
0x180036008  retn
```
