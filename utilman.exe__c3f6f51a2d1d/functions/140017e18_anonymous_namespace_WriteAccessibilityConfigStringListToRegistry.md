# _anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry

- ea: `0x140017e18`
- end: `0x140017f79`
- name: `_anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry`
- size: `353`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400170a8`

## callees

- `0x14000d75c`
- `0x14000ea8c`
- `0x14000f5f4`
- `0x140017e18`
- `0x1400180c8`
- `0x1400181b4`
- `0x14001cb14`
- `0x14001cb68`

## string_xrefs

- `0x140017e3c`: ``anonymous-namespace'::WriteAccessibilityConfigStringListToRegistry`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a3,
        const BYTE *a4)
{
  int v8; // eax
  int v9; // r8d
  const wchar_t *v10; // rdi
  _QWORD *v11; // rcx
  int v12; // edx
  unsigned int v13; // ebx
  _BYTE v15[16]; // [rsp+30h] [rbp-38h] BYREF
  HKEY v16[5]; // [rsp+40h] [rbp-28h] BYREF
  int v17; // [rsp+A0h] [rbp+38h] BYREF

  v17 = 0;
  _Trace::_Trace((_Trace *)v15, L"`anonymous-namespace'::WriteAccessibilityConfigStringListToRegistry", &v17);
  memset(v16, 0, 24);
  v8 = ATL::CRegKey::Open((ATL::CRegKey *)v16, hKey, lpSubKey, 0x20006u);
  v10 = L"HKLM";
  if ( hKey != HKEY_LOCAL_MACHINE )
    v10 = L"HKCU";
  if ( v8 )
  {
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v17 = v8;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v12 = 22;
LABEL_15:
      WPP_SF_SSd(v11[2], v12, v9, (_DWORD)v10, (__int64)lpSubKey, v8);
    }
  }
  else
  {
    v8 = ATL::CRegKey::SetStringValue(v16, a3, a4);
    if ( v8 )
    {
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      v17 = v8;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v12 = 23;
        goto LABEL_15;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, a4);
    }
  }
  v13 = v17;
  ATL::CRegKey::Close((ATL::CRegKey *)v16);
  _Trace::~_Trace((_Trace *)v15);
  return v13;
}

```

## disassembly

```asm
0x140017e18  push    rbp
0x140017e1a  push    rbx
0x140017e1b  push    rsi
0x140017e1c  push    rdi
0x140017e1d  push    r14
0x140017e1f  push    r15
0x140017e21  mov     rbp, rsp
0x140017e24  sub     rsp, 68h
0x140017e28  mov     r15, r8
0x140017e2b  mov     [rbp+arg_0], 0
0x140017e32  mov     r14, rdx
0x140017e35  lea     r8, [rbp+arg_0]; int *
0x140017e39  mov     rbx, rcx
0x140017e3c  lea     rdx, aAnonymousNames; "`anonymous-namespace'::WriteAccessibili"...
0x140017e43  lea     rcx, [rbp+var_38]; this
0x140017e47  mov     rsi, r9
0x140017e4a  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x140017e4f  mov     r9d, 20006h; unsigned int
0x140017e55  mov     [rbp+var_28], 0
0x140017e5d  mov     r8, r14; lpSubKey
0x140017e60  mov     [rbp+var_20], 0
0x140017e68  mov     rdx, rbx; hKey
0x140017e6b  mov     [rbp+var_18], 0
0x140017e73  lea     rcx, [rbp+var_28]; this
0x140017e77  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140017e7c  cmp     rbx, 0FFFFFFFF80000002h
0x140017e83  lea     rcx, aHkcu; "HKCU"
0x140017e8a  lea     rdi, aHklm; "HKLM"
0x140017e91  cmovnz  rdi, rcx
0x140017e95  test    eax, eax
0x140017e97  jz      short loc_140017ECE
0x140017e99  jle     short loc_140017EA3
0x140017e9b  movzx   eax, ax
0x140017e9e  or      eax, 80070000h
0x140017ea3  mov     [rbp+arg_0], eax
0x140017ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ead  lea     rdx, WPP_GLOBAL_Control
0x140017eb4  cmp     rcx, rdx
0x140017eb7  jz      loc_140017F54
0x140017ebd  test    byte ptr [rcx+1Ch], 8
0x140017ec1  jz      loc_140017F54
0x140017ec7  mov     edx, 16h
0x140017ecc  jmp     short loc_140017F0C
0x140017ece  mov     r8, rsi; unsigned __int16 *
0x140017ed1  lea     rcx, [rbp+var_28]; this
0x140017ed5  mov     rdx, r15; unsigned __int16 *
0x140017ed8  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x140017edd  test    eax, eax
0x140017edf  jz      short loc_140017F23
0x140017ee1  jle     short loc_140017EEB
0x140017ee3  movzx   eax, ax
0x140017ee6  or      eax, 80070000h
0x140017eeb  mov     [rbp+arg_0], eax
0x140017eee  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ef5  lea     rdx, WPP_GLOBAL_Control
0x140017efc  cmp     rcx, rdx
0x140017eff  jz      short loc_140017F54
0x140017f01  test    byte ptr [rcx+1Ch], 8
0x140017f05  jz      short loc_140017F54
0x140017f07  mov     edx, 17h
0x140017f0c  mov     rcx, [rcx+10h]
0x140017f10  mov     r9, rdi
0x140017f13  mov     [rsp+68h+var_40], eax
0x140017f17  mov     [rsp+68h+var_48], r14
0x140017f1c  call    WPP_SF_SSd
0x140017f21  jmp     short loc_140017F54
0x140017f23  mov     rcx, cs:WPP_GLOBAL_Control
0x140017f2a  lea     rdx, WPP_GLOBAL_Control
0x140017f31  cmp     rcx, rdx
0x140017f34  jz      short loc_140017F54
0x140017f36  test    byte ptr [rcx+1Ch], 10h
0x140017f3a  jz      short loc_140017F54
0x140017f3c  mov     rcx, [rcx+10h]
0x140017f40  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x140017f47  mov     edx, 18h
0x140017f4c  mov     r9, rsi
0x140017f4f  call    WPP_SF_S
0x140017f54  mov     ebx, [rbp+arg_0]
0x140017f57  lea     rcx, [rbp+var_28]; this
0x140017f5b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017f60  lea     rcx, [rbp+var_38]; this
0x140017f64  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x140017f69  mov     eax, ebx
0x140017f6b  add     rsp, 68h
0x140017f6f  pop     r15
0x140017f71  pop     r14
0x140017f73  pop     rdi
0x140017f74  pop     rsi
0x140017f75  pop     rbx
0x140017f76  pop     rbp
0x140017f77  retn
```
