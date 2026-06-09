# CThemeFile::Read(ushort const *,tagVARIANT *,IErrorLog *)

- ea: `0x180005d10`
- end: `0x180005e91`
- name: `?Read@CThemeFile@@UEAAJPEBGPEAUtagVARIANT@@PEAUIErrorLog@@@Z`
- size: `385`
- prototype: `int(CThemeFile *__hidden this, const unsigned __int16 *, struct tagVARIANT *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x180005ea0`
- `0x180006210`
- `0x18000b78c`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x180005d3c`
- `SHLWAPI!StrCmpW` at `0x180005d7d`
- `SHLWAPI!StrCmpW` at `0x180005dac`
- `SHLWAPI!StrCmpW` at `0x180005d3c`
- `SHLWAPI!StrCmpW` at `0x180005d7d`
- `SHLWAPI!StrCmpW` at `0x180005dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005e79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005e79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005e84`

## pseudocode

```c
int __fastcall CThemeFile::Read(
        CThemeFile *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3,
        struct IErrorLog *a4)
{
  int result; // eax
  CThemeFile *v8; // rsi
  int v9; // edi
  void *v10; // rcx
  unsigned __int16 *v11; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v12; // [rsp+38h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return -2147024809;
  if ( !StrCmpW(a2, L"SystemMetrics") )
  {
    result = CThemeFile::_LoadThemeMetrics((CThemeFile *)((char *)this - 32));
    a3->vt = 0x4000;
    a3->llVal = (LONGLONG)this + 36;
    return result;
  }
  if ( !StrCmpW(a2, L"DefaultMetrics") )
  {
    result = CThemeFile::_LoadDefaultThemeMetrics((CThemeFile *)((char *)this - 32), (CThemeFile *)((char *)this + 36));
    a3->vt = 0x4000;
    a3->llVal = (LONGLONG)this + 36;
    return result;
  }
  if ( StrCmpW(a2, L"Theme_HasSystemMetrics") )
    return -2147024809;
  v8 = (CThemeFile *)((char *)this - 32);
  result = CThemeFile::_LoadThemeMetrics(v8);
  a3->vt = 11;
  a3->iVal = 0;
  v9 = result;
  if ( result >= 0 )
  {
    v12 = 0;
    if ( (int)CThemeFile::_getThemeSetting(v8, L"Metrics", L"IconMetrics", 0, &v12) >= 0 )
    {
      v11 = 0;
      if ( (int)CThemeFile::_getThemeSetting(v8, L"Metrics", L"NonclientMetrics", 0, &v11) >= 0 )
      {
        pv = 0;
        if ( (int)CThemeFile::_getThemeSetting(
                    v8,
                    L"Control Panel\\Colors",
                    L"ActiveTitle",
                    0,
                    (unsigned __int16 **)&pv) >= 0 )
        {
          v10 = pv;
          a3->iVal = -1;
          CoTaskMemFree(v10);
        }
        CoTaskMemFree(v11);
      }
      CoTaskMemFree(v12);
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180005d10  mov     [rsp+arg_0], rbx
0x180005d15  mov     [rsp+arg_10], rsi
0x180005d1a  push    rdi
0x180005d1b  sub     rsp, 40h
0x180005d1f  mov     rbx, r8
0x180005d22  mov     rdi, rdx
0x180005d25  mov     rsi, rcx
0x180005d28  test    rdx, rdx
0x180005d2b  jz      short loc_180005D6C
0x180005d2d  test    rbx, rbx
0x180005d30  jz      short loc_180005D6C
0x180005d32  lea     rdx, psz2; "SystemMetrics"
0x180005d39  mov     rcx, rdi; psz1
0x180005d3c  call    cs:__imp_StrCmpW
0x180005d42  test    eax, eax
0x180005d44  jnz     short loc_180005D73
0x180005d46  lea     rcx, [rsi-20h]; this
0x180005d4a  call    ?_LoadThemeMetrics@CThemeFile@@AEAAJXZ; CThemeFile::_LoadThemeMetrics(void)
0x180005d4f  lea     rcx, [rsi+24h]
0x180005d53  mov     word ptr [rbx], 4000h
0x180005d58  mov     [rbx+8], rcx
0x180005d5c  mov     rbx, [rsp+48h+arg_0]
0x180005d61  mov     rsi, [rsp+48h+arg_10]
0x180005d66  add     rsp, 40h
0x180005d6a  pop     rdi
0x180005d6b  retn
0x180005d6c  mov     eax, 80070057h
0x180005d71  jmp     short loc_180005D5C
0x180005d73  lea     rdx, aDefaultmetrics; "DefaultMetrics"
0x180005d7a  mov     rcx, rdi; psz1
0x180005d7d  call    cs:__imp_StrCmpW
0x180005d83  test    eax, eax
0x180005d85  jnz     short loc_180005DA2
0x180005d87  lea     rdi, [rsi+24h]
0x180005d8b  mov     rdx, rdi; struct SYSTEMMETRICSALL *
0x180005d8e  lea     rcx, [rsi-20h]; this
0x180005d92  call    ?_LoadDefaultThemeMetrics@CThemeFile@@AEAAJPEAUSYSTEMMETRICSALL@@@Z; CThemeFile::_LoadDefaultThemeMetrics(SYSTEMMETRICSALL *)
0x180005d97  mov     word ptr [rbx], 4000h
0x180005d9c  mov     [rbx+8], rdi
0x180005da0  jmp     short loc_180005D5C
0x180005da2  lea     rdx, aThemeHassystem; "Theme_HasSystemMetrics"
0x180005da9  mov     rcx, rdi; psz1
0x180005dac  call    cs:__imp_StrCmpW
0x180005db2  test    eax, eax
0x180005db4  jnz     short loc_180005D6C
0x180005db6  add     rsi, 0FFFFFFFFFFFFFFE0h
0x180005dba  mov     rcx, rsi; this
0x180005dbd  call    ?_LoadThemeMetrics@CThemeFile@@AEAAJXZ; CThemeFile::_LoadThemeMetrics(void)
0x180005dc2  xor     ecx, ecx
0x180005dc4  mov     word ptr [rbx], 0Bh
0x180005dc9  mov     [rbx+8], cx
0x180005dcd  mov     edi, eax
0x180005dcf  test    eax, eax
0x180005dd1  js      short loc_180005D5C
0x180005dd3  mov     [rsp+48h+var_10], rcx
0x180005dd8  lea     rax, [rsp+48h+var_10]
0x180005ddd  mov     rcx, rsi; this
0x180005de0  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x180005de5  xor     r9d, r9d; unsigned int
0x180005de8  lea     r8, aIconmetrics; "IconMetrics"
0x180005def  lea     rdx, aMetrics; "Metrics"
0x180005df6  call    ?_getThemeSetting@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z; CThemeFile::_getThemeSetting(ushort const *,ushort const *,ulong,ushort * *)
0x180005dfb  test    eax, eax
0x180005dfd  js      loc_180005E8A
0x180005e03  lea     rax, [rsp+48h+var_18]
0x180005e08  mov     [rsp+48h+var_18], 0
0x180005e11  xor     r9d, r9d; unsigned int
0x180005e14  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x180005e19  lea     r8, aNonclientmetri_0; "NonclientMetrics"
0x180005e20  mov     rcx, rsi; this
0x180005e23  lea     rdx, aMetrics; "Metrics"
0x180005e2a  call    ?_getThemeSetting@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z; CThemeFile::_getThemeSetting(ushort const *,ushort const *,ulong,ushort * *)
0x180005e2f  test    eax, eax
0x180005e31  js      short loc_180005E7F
0x180005e33  mov     r8, cs:off_18006E530; unsigned __int16 *
0x180005e3a  lea     rax, [rsp+48h+pv]
0x180005e3f  xor     r9d, r9d; unsigned int
0x180005e42  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x180005e47  lea     rdx, aControlPanelCo; "Control Panel\\Colors"
0x180005e4e  mov     [rsp+48h+pv], 0
0x180005e57  mov     rcx, rsi; this
0x180005e5a  call    ?_getThemeSetting@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z; CThemeFile::_getThemeSetting(ushort const *,ushort const *,ulong,ushort * *)
0x180005e5f  test    eax, eax
0x180005e61  js      short loc_180005E74
0x180005e63  mov     rcx, [rsp+48h+pv]; pv
0x180005e68  mov     word ptr [rbx+8], 0FFFFh
0x180005e6e  call    cs:__imp_CoTaskMemFree
0x180005e74  mov     rcx, [rsp+48h+var_18]; pv
0x180005e79  call    cs:__imp_CoTaskMemFree
0x180005e7f  mov     rcx, [rsp+48h+var_10]; pv
0x180005e84  call    cs:__imp_CoTaskMemFree
0x180005e8a  mov     eax, edi
0x180005e8c  jmp     loc_180005D5C
```
