# IASPolicy::get_ProfileIPFilterTemplateGuid(ushort * *)

- ea: `0x180035d10`
- end: `0x180035e53`
- name: `?get_ProfileIPFilterTemplateGuid@IASPolicy@@UEAAJPEAPEAG@Z`
- size: `323`
- prototype: `int(IASPolicy *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18002cd00`
- `0x180034f44`
- `0x180035d10`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysReAllocString` at `0x180035e3b`
- `OLEAUT32!__imp_SysReAllocString` at `0x180035e3b`
- `OLEAUT32!__imp_VariantInit` at `0x180035dc4`
- `OLEAUT32!__imp_VariantInit` at `0x180035dc4`

## pseudocode

```c
__int64 __fastcall IASPolicy::get_ProfileIPFilterTemplateGuid(IASPolicy *this, unsigned __int16 **a2)
{
  int ProfileObject; // ebx
  int v5; // edx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  if ( !a2 )
    return (unsigned int)-2147467261;
  if ( *((_QWORD *)this + 16) || (ProfileObject = IASPolicy::GetProfileObject(this), ProfileObject >= 0) )
  {
    VariantInit(&pvarg);
    ProfileObject = (*(__int64 (__fastcall **)(_QWORD, __int64, VARIANTARG *))(**((_QWORD **)this + 16) + 64LL))(
                      *((_QWORD *)this + 16),
                      1025,
                      &pvarg);
    if ( ProfileObject >= 0 )
    {
      if ( pvarg.vt == 8 )
        SysReAllocString(a2, pvarg.bstrVal);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Could not get IP filter GUID property - 0x%x", ProfileObject);
      v5 = 48;
      goto LABEL_9;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetProfileObject failed with 0x%x", ProfileObject);
    v5 = 47;
LABEL_9:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids,
      (unsigned int)"NPSSDO",
      ProfileObject);
  }
  return (unsigned int)ProfileObject;
}

```

## disassembly

```asm
0x180035d10  mov     [rsp+arg_0], rbx
0x180035d15  mov     [rsp+arg_8], rsi
0x180035d1a  push    rdi
0x180035d1b  sub     rsp, 50h
0x180035d1f  xor     eax, eax
0x180035d21  xorps   xmm0, xmm0
0x180035d24  mov     qword ptr [rsp+58h+pvarg+10h], rax
0x180035d29  mov     rsi, rdx
0x180035d2c  mov     rdi, rcx
0x180035d2f  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x180035d34  test    rdx, rdx
0x180035d37  jnz     short loc_180035D43
0x180035d39  mov     ebx, 80004003h
0x180035d3e  jmp     loc_180035E41
0x180035d43  cmp     [rcx+80h], rax
0x180035d4a  jnz     short loc_180035DBF
0x180035d4c  call    ?GetProfileObject@IASPolicy@@QEAAJXZ; IASPolicy::GetProfileObject(void)
0x180035d51  mov     ebx, eax
0x180035d53  test    eax, eax
0x180035d55  jns     short loc_180035DBF
0x180035d57  mov     rax, cs:WPP_GLOBAL_Control
0x180035d5e  lea     rcx, WPP_GLOBAL_Control
0x180035d65  cmp     rax, rcx
0x180035d68  jz      loc_180035E41
0x180035d6e  cmp     byte ptr [rax+19h], 2
0x180035d72  jb      loc_180035E41
0x180035d78  test    dword ptr [rax+1Ch], 400h
0x180035d7f  jz      loc_180035E41
0x180035d85  mov     edx, ebx
0x180035d87  lea     rcx, aGetprofileobje; "GetProfileObject failed with 0x%x"
0x180035d8e  call    WppDbgPrint
0x180035d93  mov     edx, 2Fh ; '/'
0x180035d98  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d9f  lea     r9, aNpssdo; "NPSSDO"
0x180035da6  lea     r8, WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids
0x180035dad  mov     [rsp+58h+var_38], ebx
0x180035db1  mov     rcx, [rcx+10h]
0x180035db5  call    WPP_SF_sd
0x180035dba  jmp     loc_180035E41
0x180035dbf  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180035dc4  call    cs:__imp_VariantInit
0x180035dca  mov     rcx, [rdi+80h]
0x180035dd1  lea     r8, [rsp+58h+pvarg]
0x180035dd6  mov     edx, 401h
0x180035ddb  mov     rax, [rcx]
0x180035dde  mov     rax, [rax+40h]
0x180035de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035de7  mov     ebx, eax
0x180035de9  test    eax, eax
0x180035deb  jns     short loc_180035E27
0x180035ded  mov     rax, cs:WPP_GLOBAL_Control
0x180035df4  lea     rcx, WPP_GLOBAL_Control
0x180035dfb  cmp     rax, rcx
0x180035dfe  jz      short loc_180035E41
0x180035e00  cmp     byte ptr [rax+19h], 2
0x180035e04  jb      short loc_180035E41
0x180035e06  test    dword ptr [rax+1Ch], 400h
0x180035e0d  jz      short loc_180035E41
0x180035e0f  mov     edx, ebx
0x180035e11  lea     rcx, aCouldNotGetIpF; "Could not get IP filter GUID property -"...
0x180035e18  call    WppDbgPrint
0x180035e1d  mov     edx, 30h ; '0'
0x180035e22  jmp     loc_180035D98
0x180035e27  mov     eax, 8
0x180035e2c  cmp     ax, word ptr [rsp+58h+pvarg]
0x180035e31  jnz     short loc_180035E41
0x180035e33  mov     rdx, qword ptr [rsp+58h+pvarg+8]; psz
0x180035e38  mov     rcx, rsi; pbstr
0x180035e3b  call    cs:__imp_SysReAllocString
0x180035e41  mov     rsi, [rsp+58h+arg_8]
0x180035e46  mov     eax, ebx
0x180035e48  mov     rbx, [rsp+58h+arg_0]
0x180035e4d  add     rsp, 50h
0x180035e51  pop     rdi
0x180035e52  retn
```
