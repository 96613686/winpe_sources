# CLogonUser::_PutAccountType(tagVARIANT const &)

- ea: `0x18002d85c`
- end: `0x18002da4f`
- name: `?_PutAccountType@CLogonUser@@AEAAJAEBUtagVARIANT@@@Z`
- size: `499`
- prototype: `int(CLogonUser *__hidden this, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f360`

## callees

- `0x180006f2c`
- `0x18002d85c`
- `0x180032248`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002d92e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002d92e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002da19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002da19`
- `OLEAUT32!__imp_VariantInit` at `0x18002d89f`
- `OLEAUT32!__imp_VariantInit` at `0x18002d89f`
- `OLEAUT32!__imp_VariantClear` at `0x18002da24`
- `OLEAUT32!__imp_VariantClear` at `0x18002da24`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d8ad`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d8ad`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002d8e8`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002d8e8`
- `samcli!NetLocalGroupAddMembers` at `0x18002d99b`
- `samcli!NetLocalGroupAddMembers` at `0x18002d99b`
- `samcli!NetLocalGroupDelMembers` at `0x18002d9f4`
- `samcli!NetLocalGroupDelMembers` at `0x18002d9f4`

## pseudocode

```c
__int64 __fastcall CLogonUser::_PutAccountType(CLogonUser *this, const struct tagVARIANT *a2)
{
  int v4; // ebx
  const WCHAR *bstrVal; // rcx
  signed int v6; // eax
  LONG lVal; // eax
  unsigned int i; // edi
  LPWSTR ppwsz; // [rsp+30h] [rbp-D0h] BYREF
  BYTE buf[8]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v13[256]; // [rsp+60h] [rbp-A0h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = VariantCopy(&pvarg, a2);
  if ( v4 >= 0 )
  {
    ppwsz = 0;
    if ( pvarg.vt != 8 )
    {
      v4 = VariantChangeType(&pvarg, &pvarg, 0, 3u);
      if ( v4 < 0 )
      {
LABEL_24:
        CoTaskMemFree(ppwsz);
        goto LABEL_25;
      }
      if ( pvarg.lVal < 0 || (unsigned __int64)pvarg.lVal >= 4 )
      {
        v4 = -2147024809;
      }
      else if ( pvarg.lVal != *((_DWORD *)this + 791) )
      {
        bstrVal = (const WCHAR *)*(&g_rggroupname_map + 4 * pvarg.lVal + 3);
LABEL_10:
        v4 = SHStrDupW(bstrVal, &ppwsz);
      }
      if ( v4 < 0 )
        goto LABEL_24;
      *(_QWORD *)buf = 0;
      v4 = StringCchPrintfW(v13, 0x100u, L"%s\\%s", (char *)this + 526, (char *)this + 12);
      if ( v4 < 0 )
        goto LABEL_24;
      *(_QWORD *)buf = v13;
      v6 = NetLocalGroupAddMembers(0, ppwsz, 3u, buf, 1u);
      if ( !v6 || v6 == 1378 )
      {
        if ( pvarg.vt != 8 )
        {
          lVal = pvarg.lVal;
          *((_DWORD *)this + 791) = pvarg.lVal;
          for ( i = lVal + 1; i < 4; ++i )
            NetLocalGroupDelMembers(0, (LPCWSTR)*(&g_rggroupname_map + 4 * (int)i + 3), 3u, buf, 1u);
          goto LABEL_24;
        }
        v6 = RemoveFromLocalGroups(v13, ppwsz);
      }
      else if ( v6 > 0 )
      {
        v4 = (unsigned __int16)v6 | 0x80070000;
        goto LABEL_24;
      }
      v4 = v6;
      goto LABEL_24;
    }
    bstrVal = pvarg.bstrVal;
    goto LABEL_10;
  }
LABEL_25:
  VariantClear(&pvarg);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002d85c  mov     [rsp-8+arg_10], rbx
0x18002d861  push    rbp
0x18002d862  push    rdi
0x18002d863  push    r15
0x18002d865  lea     rbp, [rsp-170h]
0x18002d86d  sub     rsp, 270h
0x18002d874  mov     rax, cs:__security_cookie
0x18002d87b  xor     rax, rsp
0x18002d87e  mov     [rbp+180h+var_20], rax
0x18002d885  mov     rdi, rcx
0x18002d888  xorps   xmm0, xmm0
0x18002d88b  xor     eax, eax
0x18002d88d  lea     rcx, [rsp+280h+pvarg]; pvarg
0x18002d892  movups  xmmword ptr [rsp+280h+pvarg], xmm0
0x18002d897  mov     qword ptr [rsp+280h+pvarg+10h], rax
0x18002d89c  mov     rbx, rdx
0x18002d89f  call    cs:__imp_VariantInit
0x18002d8a5  mov     rdx, rbx; pvargSrc
0x18002d8a8  lea     rcx, [rsp+280h+pvarg]; pvargDest
0x18002d8ad  call    cs:__imp_VariantCopy
0x18002d8b3  mov     ebx, eax
0x18002d8b5  test    eax, eax
0x18002d8b7  js      loc_18002DA1F
0x18002d8bd  cmp     word ptr [rsp+280h+pvarg], 8
0x18002d8c3  lea     r15, ?g_rggroupname_map@@3PAUGROUPNAME_MAP@@A; GROUPNAME_MAP near * g_rggroupname_map
0x18002d8ca  mov     [rsp+280h+ppwsz], 0
0x18002d8d3  jz      short loc_18002D924
0x18002d8d5  mov     r9d, 3; vt
0x18002d8db  lea     rdx, [rsp+280h+pvarg]; pvarSrc
0x18002d8e0  xor     r8d, r8d; wFlags
0x18002d8e3  lea     rcx, [rsp+280h+pvarg]; pvargDest
0x18002d8e8  call    cs:__imp_VariantChangeType
0x18002d8ee  mov     ebx, eax
0x18002d8f0  test    eax, eax
0x18002d8f2  js      loc_18002DA14
0x18002d8f8  mov     rax, qword ptr [rsp+280h+pvarg+8]
0x18002d8fd  test    eax, eax
0x18002d8ff  js      short loc_18002D91D
0x18002d901  movsxd  rcx, eax
0x18002d904  cmp     rcx, 4
0x18002d908  jnb     short loc_18002D91D
0x18002d90a  cmp     eax, [rdi+0C5Ch]
0x18002d910  jz      short loc_18002D936
0x18002d912  shl     rcx, 5
0x18002d916  mov     rcx, [rcx+r15+18h]
0x18002d91b  jmp     short loc_18002D929
0x18002d91d  mov     ebx, 80070057h
0x18002d922  jmp     short loc_18002D936
0x18002d924  mov     rcx, qword ptr [rsp+280h+pvarg+8]; psz
0x18002d929  lea     rdx, [rsp+280h+ppwsz]; ppwsz
0x18002d92e  call    cs:__imp_SHStrDupW
0x18002d934  mov     ebx, eax
0x18002d936  test    ebx, ebx
0x18002d938  js      loc_18002DA14
0x18002d93e  lea     rax, [rdi+0Ch]
0x18002d942  mov     qword ptr [rsp+280h+buf], 0
0x18002d94b  lea     r9, [rdi+20Eh]
0x18002d952  mov     qword ptr [rsp+280h+totalentries], rax
0x18002d957  lea     r8, aSS; "%s\\%s"
0x18002d95e  mov     edx, 100h; unsigned __int64
0x18002d963  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x18002d968  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d96d  mov     ebx, eax
0x18002d96f  test    eax, eax
0x18002d971  js      loc_18002DA14
0x18002d977  mov     rdx, [rsp+280h+ppwsz]; groupname
0x18002d97c  lea     rax, [rsp+280h+var_220]
0x18002d981  lea     r9, [rsp+280h+buf]; buf
0x18002d986  mov     qword ptr [rsp+280h+buf], rax
0x18002d98b  mov     r8d, 3; level
0x18002d991  mov     [rsp+280h+totalentries], 1; totalentries
0x18002d999  xor     ecx, ecx; servername
0x18002d99b  call    cs:__imp_NetLocalGroupAddMembers
0x18002d9a1  test    eax, eax
0x18002d9a3  jz      short loc_18002D9BB
0x18002d9a5  cmp     eax, 562h
0x18002d9aa  jz      short loc_18002D9BB
0x18002d9ac  test    eax, eax
0x18002d9ae  jle     short loc_18002DA12
0x18002d9b0  movzx   ebx, ax
0x18002d9b3  or      ebx, 80070000h
0x18002d9b9  jmp     short loc_18002DA14
0x18002d9bb  cmp     word ptr [rsp+280h+pvarg], 8
0x18002d9c1  jz      short loc_18002DA03
0x18002d9c3  mov     rax, qword ptr [rsp+280h+pvarg+8]
0x18002d9c8  mov     [rdi+0C5Ch], eax
0x18002d9ce  lea     edi, [rax+1]
0x18002d9d1  jmp     short loc_18002D9FC
0x18002d9d3  movsxd  rdx, edi
0x18002d9d6  lea     r9, [rsp+280h+buf]; buf
0x18002d9db  shl     rdx, 5
0x18002d9df  mov     r8d, 3; level
0x18002d9e5  xor     ecx, ecx; servername
0x18002d9e7  mov     [rsp+280h+totalentries], 1; totalentries
0x18002d9ef  mov     rdx, [rdx+r15+18h]; groupname
0x18002d9f4  call    cs:__imp_NetLocalGroupDelMembers
0x18002d9fa  inc     edi
0x18002d9fc  cmp     edi, 4
0x18002d9ff  jb      short loc_18002D9D3
0x18002da01  jmp     short loc_18002DA14
0x18002da03  mov     rdx, [rsp+280h+ppwsz]; unsigned __int16 *
0x18002da08  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x18002da0d  call    ?RemoveFromLocalGroups@@YAJPEBG0@Z; RemoveFromLocalGroups(ushort const *,ushort const *)
0x18002da12  mov     ebx, eax
0x18002da14  mov     rcx, [rsp+280h+ppwsz]; pv
0x18002da19  call    cs:__imp_CoTaskMemFree
0x18002da1f  lea     rcx, [rsp+280h+pvarg]; pvarg
0x18002da24  call    cs:__imp_VariantClear
0x18002da2a  mov     eax, ebx
0x18002da2c  mov     rcx, [rbp+180h+var_20]
0x18002da33  xor     rcx, rsp; StackCookie
0x18002da36  call    __security_check_cookie
0x18002da3b  mov     rbx, [rsp+280h+arg_10]
0x18002da43  add     rsp, 270h
0x18002da4a  pop     r15
0x18002da4c  pop     rdi
0x18002da4d  pop     rbp
0x18002da4e  retn
```
