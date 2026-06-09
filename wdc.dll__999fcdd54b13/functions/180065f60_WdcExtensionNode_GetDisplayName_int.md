# WdcExtensionNode::GetDisplayName(int)

- ea: `0x180065f60`
- end: `0x18006607a`
- name: `?GetDisplayName@WdcExtensionNode@@UEAAPEAGH@Z`
- size: `282`
- prototype: `unsigned __int16 *__fastcall(WdcExtensionNode *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800044ac`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x180065f60`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006601f`
- `OLEAUT32!__imp_SysAllocString` at `0x18006601f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006600b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006600b`

## string_xrefs

- `0x180065faf`: `base\diagnosis\pdui\perfmon\mmc\extension.cpp`
- `0x180065ff1`: `base\diagnosis\pdui\perfmon\mmc\extension.cpp`
- `0x180065fa8`: `WdcExtensionNode::GetDisplayName`
- `0x180065fea`: `WdcExtensionNode::GetDisplayName`

## pseudocode

```c
unsigned __int16 *__fastcall WdcExtensionNode::GetDisplayName(WdcExtensionNode *this, const char *a2, int a3)
{
  _WORD *v4; // rcx
  WCHAR *v5; // rdi
  int String; // eax
  const char *v7; // rdx
  int v8; // r8d
  OLECHAR *v9; // rcx
  BSTR v10; // rax
  __int64 v12; // [rsp+20h] [rbp-18h]

  v4 = (_WORD *)*((_QWORD *)this + 18);
  if ( !v4 || !*v4 )
  {
    v5 = (WCHAR *)WdcAlloc(0x400u, a2, a3);
    if ( !v5 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\extension.cpp",
        "WdcExtensionNode::GetDisplayName",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      return (unsigned __int16 *)*((_QWORD *)this + 18);
    }
    *v5 = 0;
    String = WdcLoadString(0x2725u, v5, 0x200u);
    if ( String >= 0 )
    {
      v9 = (OLECHAR *)*((_QWORD *)this + 18);
      if ( v9 )
      {
        SysFreeString(v9);
        *((_QWORD *)this + 18) = 0;
      }
      v10 = SysAllocString(v5);
      if ( v10 )
      {
        *((_QWORD *)this + 18) = v10;
        goto LABEL_13;
      }
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      LODWORD(v12) = -2147024882;
    }
    else
    {
      LODWORD(v12) = String;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\extension.cpp",
      "WdcExtensionNode::GetDisplayName",
      0,
      L"FAILURE: 0x%08x",
      v12);
LABEL_13:
    WdcFree(v5, v7, v8);
  }
  return (unsigned __int16 *)*((_QWORD *)this + 18);
}

```

## disassembly

```asm
0x180065f60  mov     [rsp+arg_0], rbx
0x180065f65  push    rdi
0x180065f66  sub     rsp, 30h
0x180065f6a  mov     rbx, rcx
0x180065f6d  mov     rcx, [rcx+90h]
0x180065f74  test    rcx, rcx
0x180065f77  jz      short loc_180065F84
0x180065f79  xor     eax, eax
0x180065f7b  cmp     ax, [rcx]
0x180065f7e  jnz     loc_180066068
0x180065f84  mov     ecx, 400h; dwBytes
0x180065f89  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180065f8e  mov     rdi, rax
0x180065f91  test    rax, rax
0x180065f94  jnz     short loc_180065FC0
0x180065f96  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180065f9d  mov     dword ptr [rsp+38h+var_18], 8007000Eh
0x180065fa5  xor     r8d, r8d; int
0x180065fa8  lea     rdx, aWdcextensionno_0; "WdcExtensionNode::GetDisplayName"
0x180065faf  lea     rcx, aBaseDiagnosisP_47; "base\\diagnosis\\pdui\\perfmon\\mmc\\ex"...
0x180065fb6  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180065fbb  jmp     loc_180066068
0x180065fc0  xor     eax, eax
0x180065fc2  mov     r8d, 200h; cchBufferMax
0x180065fc8  mov     rdx, rdi; lpBuffer
0x180065fcb  mov     [rdi], ax
0x180065fce  mov     ecx, 2725h; uID
0x180065fd3  call    ?WdcLoadString@@YAJKPEAG_K@Z; WdcLoadString(ulong,ushort *,unsigned __int64)
0x180065fd8  test    eax, eax
0x180065fda  jns     short loc_180065FFF
0x180065fdc  mov     dword ptr [rsp+38h+var_18], eax
0x180065fe0  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180065fe7  xor     r8d, r8d; int
0x180065fea  lea     rdx, aWdcextensionno_0; "WdcExtensionNode::GetDisplayName"
0x180065ff1  lea     rcx, aBaseDiagnosisP_47; "base\\diagnosis\\pdui\\perfmon\\mmc\\ex"...
0x180065ff8  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180065ffd  jmp     short loc_180066060
0x180065fff  mov     rcx, [rbx+90h]; bstrString
0x180066006  test    rcx, rcx
0x180066009  jz      short loc_18006601C
0x18006600b  call    cs:__imp_SysFreeString
0x180066011  mov     qword ptr [rbx+90h], 0
0x18006601c  mov     rcx, rdi; psz
0x18006601f  call    cs:__imp_SysAllocString
0x180066025  test    rax, rax
0x180066028  jnz     short loc_180066059
0x18006602a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180066031  mov     dword ptr [rsp+38h+var_18], 8007000Eh
0x180066039  xor     r8d, r8d; int
0x18006603c  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180066043  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18006604a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18006604f  mov     dword ptr [rsp+38h+var_18], 8007000Eh
0x180066057  jmp     short loc_180065FE0
0x180066059  mov     [rbx+90h], rax
0x180066060  mov     rcx, rdi; void *
0x180066063  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180066068  mov     rax, [rbx+90h]
0x18006606f  mov     rbx, [rsp+38h+arg_0]
0x180066074  add     rsp, 30h
0x180066078  pop     rdi
0x180066079  retn
```
