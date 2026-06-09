# ATL::CAxHostWindow::TranslateAcceleratorW(tagMSG *,_GUID const *,ulong)

- ea: `0x140008b20`
- end: `0x140008bdc`
- name: `?TranslateAcceleratorW@CAxHostWindow@ATL@@UEAAJPEAUtagMSG@@PEBU_GUID@@K@Z`
- size: `188`
- prototype: `int(ATL::CAxHostWindow *__hidden this, struct tagMSG *, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140008b20`
- `0x14000f010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140008b7d`
- `ole32!CoTaskMemFree` at `0x140008b7d`
- `ole32!StringFromCLSID` at `0x140008b64`
- `ole32!StringFromCLSID` at `0x140008b64`
- `OLEAUT32!__imp_SysAllocString` at `0x140008b6f`
- `OLEAUT32!__imp_SysAllocString` at `0x140008b6f`
- `OLEAUT32!__imp_SysFreeString` at `0x140008bba`
- `OLEAUT32!__imp_SysFreeString` at `0x140008bba`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::TranslateAcceleratorW(
        ATL::CAxHostWindow *this,
        struct tagMSG *a2,
        const struct _GUID *a3,
        int a4)
{
  __int64 *v4; // rsi
  __int64 result; // rax
  __int64 v8; // rax
  void (__fastcall *v9)(__int64 *, _QWORD, _QWORD, _QWORD, _DWORD, OLECHAR *, int, unsigned int *); // rdi
  OLECHAR *v10; // rbx
  OLECHAR *psz; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+80h] [rbp+8h] BYREF

  v4 = (__int64 *)*((_QWORD *)this + 10);
  result = 1;
  v12 = 1;
  if ( v4 )
  {
    v8 = *v4;
    psz = 0;
    v9 = *(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _DWORD, OLECHAR *, int, unsigned int *))(v8 + 128);
    StringFromCLSID(a3, &psz);
    v10 = SysAllocString(psz);
    CoTaskMemFree(psz);
    v9(v4, LODWORD(a2->hwnd), a2->message, LODWORD(a2->wParam), a2->lParam, v10, a4, &v12);
    SysFreeString(v10);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x140008b20  mov     r11, rsp
0x140008b23  mov     [r11+10h], rbx
0x140008b27  mov     [r11+18h], rbp
0x140008b2b  push    rsi
0x140008b2c  push    rdi
0x140008b2d  push    r14
0x140008b2f  sub     rsp, 60h
0x140008b33  mov     rsi, [rcx+50h]
0x140008b37  mov     eax, 1
0x140008b3c  mov     [r11+8], eax
0x140008b40  mov     ebp, r9d
0x140008b43  mov     r14, rdx
0x140008b46  test    rsi, rsi
0x140008b49  jz      short loc_140008BC7
0x140008b4b  mov     rax, [rsi]
0x140008b4e  lea     rdx, [r11-28h]; lplpsz
0x140008b52  mov     rcx, r8; rclsid
0x140008b55  mov     qword ptr [r11-28h], 0
0x140008b5d  mov     rdi, [rax+80h]
0x140008b64  call    cs:__imp_StringFromCLSID
0x140008b6a  mov     rcx, [rsp+78h+psz]; psz
0x140008b6f  call    cs:__imp_SysAllocString
0x140008b75  mov     rcx, [rsp+78h+psz]; pv
0x140008b7a  mov     rbx, rax
0x140008b7d  call    cs:__imp_CoTaskMemFree
0x140008b83  mov     edx, [r14+18h]
0x140008b87  lea     rax, [rsp+78h+arg_0]
0x140008b8f  mov     r9d, [r14+10h]
0x140008b93  mov     rcx, rsi
0x140008b96  mov     r8d, [r14+8]
0x140008b9a  mov     [rsp+78h+var_40], rax
0x140008b9f  mov     rax, rdi
0x140008ba2  mov     [rsp+78h+var_48], ebp
0x140008ba6  mov     [rsp+78h+var_50], rbx
0x140008bab  mov     [rsp+78h+var_58], edx
0x140008baf  mov     edx, [r14]
0x140008bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008bb7  mov     rcx, rbx; bstrString
0x140008bba  call    cs:__imp_SysFreeString
0x140008bc0  mov     eax, [rsp+78h+arg_0]
0x140008bc7  lea     r11, [rsp+78h+var_18]
0x140008bcc  mov     rbx, [r11+28h]
0x140008bd0  mov     rbp, [r11+30h]
0x140008bd4  mov     rsp, r11
0x140008bd7  pop     r14
0x140008bd9  pop     rdi
0x140008bda  pop     rsi
0x140008bdb  retn
```
