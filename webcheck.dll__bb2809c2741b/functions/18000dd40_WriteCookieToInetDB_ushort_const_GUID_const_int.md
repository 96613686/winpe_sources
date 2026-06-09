# WriteCookieToInetDB(ushort const *,_GUID const *,int)

- ea: `0x18000dd40`
- end: `0x18000ddd2`
- name: `?WriteCookieToInetDB@@YAJPEBGPEBU_GUID@@H@Z`
- size: `146`
- prototype: `__int64 __fastcall(const unsigned __int16 *, IID *rclsid, int)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000a4d0`
- `0x18000b514`
- `0x18000b880`
- `0x18000cc84`
- `0x18000e28c`
- `0x18000e3c4`
- `0x180018a40`

## callees

- `0x18000c1d0`
- `0x18000dd40`

## import_xrefs

- `ole32!StringFromCLSID` at `0x18000dd73`
- `ole32!StringFromCLSID` at `0x18000dd73`
- `ole32!CoTaskMemFree` at `0x18000ddbf`
- `ole32!CoTaskMemFree` at `0x18000ddbf`

## pseudocode

```c
__int64 __fastcall WriteCookieToInetDB(const unsigned __int16 *a1, IID *rclsid, int a3, unsigned int a4)
{
  unsigned int v7; // ebx
  struct tagPROPVARIANT v8; // [rsp+30h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  memset(&v8, 0, sizeof(v8));
  if ( !a3 )
  {
    if ( StringFromCLSID(rclsid, (LPOLESTR *)&pv) < 0 )
      return 2147500037LL;
    v8.vt = 31;
    v8.hVal.QuadPart = (LONGLONG)pv;
  }
  v7 = IntSiteHelper(a1, &c_rgPropRead, &v8, a4, 1);
  if ( !a3 )
    CoTaskMemFree(pv);
  return v7;
}

```

## disassembly

```asm
0x18000dd40  mov     r11, rsp
0x18000dd43  mov     [r11+8], rbx
0x18000dd47  push    rdi
0x18000dd48  sub     rsp, 50h
0x18000dd4c  mov     rbx, rcx
0x18000dd4f  xorps   xmm0, xmm0
0x18000dd52  xor     ecx, ecx
0x18000dd54  mov     edi, r8d
0x18000dd57  mov     [r11+20h], rcx
0x18000dd5b  mov     rax, rdx
0x18000dd5e  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x18000dd63  mov     [r11-18h], rcx
0x18000dd67  test    r8d, r8d
0x18000dd6a  jnz     short loc_18000DD98
0x18000dd6c  lea     rdx, [r11+20h]; lplpsz
0x18000dd70  mov     rcx, rax; rclsid
0x18000dd73  call    cs:__imp_StringFromCLSID
0x18000dd79  test    eax, eax
0x18000dd7b  jns     short loc_18000DD84
0x18000dd7d  mov     eax, 80004005h
0x18000dd82  jmp     short loc_18000DDC7
0x18000dd84  mov     eax, 1Fh
0x18000dd89  mov     word ptr [rsp+58h+var_28], ax
0x18000dd8e  mov     rax, [rsp+58h+pv]
0x18000dd93  mov     qword ptr [rsp+58h+var_28+8], rax
0x18000dd98  lea     r8, [rsp+58h+var_28]; struct tagPROPVARIANT *
0x18000dd9d  mov     [rsp+58h+var_38], 1; int
0x18000dda5  lea     rdx, ?c_rgPropRead@@3QBUtagPROPSPEC@@B; struct tagPROPSPEC *
0x18000ddac  mov     rcx, rbx; unsigned __int16 *
0x18000ddaf  call    ?IntSiteHelper@@YAJPEBGPEBUtagPROPSPEC@@PEAUtagPROPVARIANT@@IH@Z; IntSiteHelper(ushort const *,tagPROPSPEC const *,tagPROPVARIANT *,uint,int)
0x18000ddb4  mov     ebx, eax
0x18000ddb6  test    edi, edi
0x18000ddb8  jnz     short loc_18000DDC5
0x18000ddba  mov     rcx, [rsp+58h+pv]; pv
0x18000ddbf  call    cs:__imp_CoTaskMemFree
0x18000ddc5  mov     eax, ebx
0x18000ddc7  mov     rbx, [rsp+58h+arg_0]
0x18000ddcc  add     rsp, 50h
0x18000ddd0  pop     rdi
0x18000ddd1  retn
```
