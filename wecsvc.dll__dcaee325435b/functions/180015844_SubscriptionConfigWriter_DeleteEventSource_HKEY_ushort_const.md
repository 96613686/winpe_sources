# SubscriptionConfigWriter::DeleteEventSource(HKEY__ *,ushort const *)

- ea: `0x180015844`
- end: `0x1800159d7`
- name: `?DeleteEventSource@SubscriptionConfigWriter@@AEAAXPEAUHKEY__@@PEBG@Z`
- size: `403`
- prototype: `void __fastcall(SubscriptionConfigWriter *this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001718c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003e6c`
- `0x180015844`
- `0x1800159e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001587a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001587a`
- `ADVAPI32!RegDeleteKeyW` at `0x180015944`
- `ADVAPI32!RegDeleteKeyW` at `0x180015944`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SubscriptionConfigWriter::DeleteEventSource(
        SubscriptionConfigWriter *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char v8; // [rsp+38h] [rbp-40h]
  const char *v9; // [rsp+40h] [rbp-38h]
  __int64 v10; // [rsp+48h] [rbp-30h]
  __int64 v11; // [rsp+50h] [rbp-28h]
  unsigned int v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+5Ch] [rbp-1Ch]
  int v14; // [rsp+60h] [rbp-18h]
  HKEY hKey; // [rsp+A0h] [rbp+28h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey);
  if ( v5 == 2 )
  {
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  }
  else
  {
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v5);
      }
      v8 = 0;
      v9 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v10 = 0;
      v11 = 0;
      v12 = v5;
      v13 = -1;
      v14 = 843;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    SubscriptionConfigWriter::DeletePassword(hKey, L"TargetId");
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    v6 = RegDeleteKeyW(a2, a3);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v6);
      }
      v8 = 0;
      v9 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v10 = 0;
      v11 = 0;
      v12 = v6;
      v13 = -1;
      v14 = 852;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180015844  mov     [rsp-20h+hKey], rcx
0x180015849  push    rbp
0x18001584a  push    rbx
0x18001584b  push    rsi
0x18001584c  push    rdi
0x18001584d  mov     rbp, rsp
0x180015850  sub     rsp, 78h
0x180015854  mov     rdi, r8
0x180015857  mov     rsi, rdx
0x18001585a  mov     [rbp+hKey], 0
0x180015862  lea     rax, [rbp+hKey]
0x180015866  mov     [rsp+78h+phkResult], rax; phkResult
0x18001586b  mov     r9d, 20019h; samDesired
0x180015871  xor     r8d, r8d; ulOptions
0x180015874  mov     rdx, rdi; lpSubKey
0x180015877  mov     rcx, rsi; hKey
0x18001587a  call    cs:__imp_RegOpenKeyExW
0x180015880  mov     ebx, eax
0x180015882  cmp     eax, 2
0x180015885  jnz     short loc_180015899
0x180015887  lea     rcx, [rbp+hKey]; this
0x18001588b  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180015890  add     rsp, 78h
0x180015894  pop     rdi
0x180015895  pop     rsi
0x180015896  pop     rbx
0x180015897  pop     rbp
0x180015898  retn
0x180015899  test    ebx, ebx
0x18001589b  jz      loc_180015924
0x1800158a1  lea     rax, WPP_GLOBAL_Control
0x1800158a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158af  cmp     rcx, rax
0x1800158b2  jz      short loc_1800158D8
0x1800158b4  test    byte ptr [rcx+1Ch], 40h
0x1800158b8  jz      short loc_1800158D8
0x1800158ba  cmp     byte ptr [rcx+19h], 2
0x1800158be  jb      short loc_1800158D8
0x1800158c0  mov     edx, 1Ch
0x1800158c5  mov     r9d, ebx
0x1800158c8  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x1800158cf  mov     rcx, [rcx+10h]
0x1800158d3  call    WPP_SF_D
0x1800158d8  mov     [rbp+var_40], 0
0x1800158dc  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800158e3  mov     [rbp+var_38], rax
0x1800158e7  mov     [rbp+var_30], 0
0x1800158ef  mov     [rbp+var_28], 0
0x1800158f7  mov     [rbp+var_20], ebx
0x1800158fa  mov     [rbp+var_1C], 0FFFFFFFFh
0x180015901  mov     [rbp+var_18], 34Bh
0x180015908  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001590f  mov     [rbp+pExceptionObject], rax
0x180015913  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001591a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001591e  call    _CxxThrowException_0
0x180015924  lea     rdx, aTargetid; "TargetId"
0x18001592b  mov     rcx, [rbp+hKey]; hKey
0x18001592f  call    ?DeletePassword@SubscriptionConfigWriter@@CAXPEAUHKEY__@@PEBG@Z; SubscriptionConfigWriter::DeletePassword(HKEY__ *,ushort const *)
0x180015934  nop
0x180015935  lea     rcx, [rbp+hKey]; this
0x180015939  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18001593e  mov     rdx, rdi; lpSubKey
0x180015941  mov     rcx, rsi; hKey
0x180015944  call    cs:__imp_RegDeleteKeyW
0x18001594a  mov     ebx, eax
0x18001594c  test    eax, eax
0x18001594e  jz      loc_180015890
0x180015954  lea     rax, WPP_GLOBAL_Control
0x18001595b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015962  cmp     rcx, rax
0x180015965  jz      short loc_18001598B
0x180015967  test    byte ptr [rcx+1Ch], 40h
0x18001596b  jz      short loc_18001598B
0x18001596d  cmp     byte ptr [rcx+19h], 2
0x180015971  jb      short loc_18001598B
0x180015973  mov     edx, 1Dh
0x180015978  mov     r9d, ebx
0x18001597b  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180015982  mov     rcx, [rcx+10h]
0x180015986  call    WPP_SF_D
0x18001598b  mov     [rbp+var_40], 0
0x18001598f  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x180015996  mov     [rbp+var_38], rax
0x18001599a  mov     [rbp+var_30], 0
0x1800159a2  mov     [rbp+var_28], 0
0x1800159aa  mov     [rbp+var_20], ebx
0x1800159ad  mov     [rbp+var_1C], 0FFFFFFFFh
0x1800159b4  mov     [rbp+var_18], 354h
0x1800159bb  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800159c2  mov     [rbp+pExceptionObject], rax
0x1800159c6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800159cd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800159d1  call    _CxxThrowException_0
```
