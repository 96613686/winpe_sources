# VPNIKEClientConnection::DispatchUpdateConnection(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180017a60`
- end: `0x180017c4d`
- name: `?DispatchUpdateConnection@VPNIKEClientConnection@@KAKPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct _TP_CALLBACK_INSTANCE *, _QWORD *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x180007a0c`
- `0x180017a60`
- `0x18005d9ac`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017bef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017bef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017be1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017be1`
- `RASAPI32!RasUpdateConnection` at `0x180017b57`
- `RASAPI32!RasUpdateConnection` at `0x180017b57`

## string_xrefs

- `0x180017ae7`: `Calling RasUpdateConnection for Conn: 0x%x`
- `0x180017b7b`: `RasUpdateConnection failed with %!WINERROR!`

## pseudocode

```c
__int64 __fastcall VPNIKEClientConnection::DispatchUpdateConnection(
        struct _TP_CALLBACK_INSTANCE *a1,
        _QWORD *a2,
        struct _TP_WORK *a3)
{
  PVOID *v4; // rbx
  __int64 v5; // r8
  DWORD updated; // eax
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  int v10; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v11[2044]; // [rsp+24h] [rbp-814h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( (byte_1800AA941 & 8) != 0 )
  {
    v5 = *a2;
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"Calling RasUpdateConnection for Conn: 0x%x", v5);
    if ( (byte_1800AA941 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v10);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_q(v4[2], 79, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, *a2);
  updated = RasUpdateConnection((HRASCONN)*a2, (struct tagRASUPDATECONN *)(a2 + 2));
  v7 = updated;
  if ( updated )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"RasUpdateConnection failed with %!WINERROR!", updated);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v10);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, v7);
    }
  }
  BaseConnection::DeleteRef((BaseConnection *)a2[1]);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180017a60  mov     [rsp+arg_0], rbx
0x180017a65  mov     [rsp+arg_10], rdi
0x180017a6a  push    r14
0x180017a6c  sub     rsp, 830h
0x180017a73  mov     rax, cs:__security_cookie
0x180017a7a  xor     rax, rsp
0x180017a7d  mov     [rsp+838h+var_18], rax
0x180017a85  mov     rdi, rdx
0x180017a88  mov     rbx, cs:WPP_GLOBAL_Control
0x180017a8f  lea     r14, WPP_GLOBAL_Control
0x180017a96  cmp     rbx, r14
0x180017a99  jz      short loc_180017AC3
0x180017a9b  test    byte ptr [rbx+1Ch], 1
0x180017a9f  jz      short loc_180017AC3
0x180017aa1  cmp     byte ptr [rbx+19h], 6
0x180017aa5  jb      short loc_180017AC3
0x180017aa7  mov     rcx, [rbx+10h]
0x180017aab  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180017ab2  mov     edx, 4Eh ; 'N'
0x180017ab7  call    WPP_SF_
0x180017abc  mov     rbx, cs:WPP_GLOBAL_Control
0x180017ac3  xor     eax, eax
0x180017ac5  lea     rcx, [rsp+838h+var_814]; void *
0x180017aca  xor     edx, edx; Val
0x180017acc  mov     [rsp+838h+var_818], eax
0x180017ad0  mov     r8d, 7FCh; Size
0x180017ad6  call    memset_0
0x180017adb  test    cs:byte_1800AA941, 8
0x180017ae2  jz      short loc_180017B27
0x180017ae4  mov     r8, [rdi]
0x180017ae7  lea     rdx, aCallingRasupda; "Calling RasUpdateConnection for Conn: 0"...
0x180017aee  xor     eax, eax
0x180017af0  lea     rcx, [rsp+838h+var_818]
0x180017af5  mov     word ptr [rsp+838h+var_818], ax
0x180017afa  call    FormatRRASErrorString
0x180017aff  test    cs:byte_1800AA941, 8
0x180017b06  jz      short loc_180017B20
0x180017b08  lea     r8, [rsp+838h+var_818]
0x180017b0d  lea     rdx, RasVpnIkeTraceInfo
0x180017b14  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017b1b  call    McTemplateU0z_EventWriteTransfer
0x180017b20  mov     rbx, cs:WPP_GLOBAL_Control
0x180017b27  cmp     rbx, r14
0x180017b2a  jz      short loc_180017B50
0x180017b2c  test    byte ptr [rbx+1Ch], 1
0x180017b30  jz      short loc_180017B50
0x180017b32  cmp     byte ptr [rbx+19h], 5
0x180017b36  jb      short loc_180017B50
0x180017b38  mov     r9, [rdi]
0x180017b3b  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180017b42  mov     rcx, [rbx+10h]
0x180017b46  mov     edx, 4Fh ; 'O'
0x180017b4b  call    WPP_SF_q
0x180017b50  mov     rcx, [rdi]; hrasconn
0x180017b53  lea     rdx, [rdi+10h]; lprasupdateconn
0x180017b57  call    cs:__imp_RasUpdateConnection
0x180017b5d  mov     ebx, eax
0x180017b5f  test    eax, eax
0x180017b61  jz      short loc_180017BD8
0x180017b63  test    cs:byte_1800AA941, 4
0x180017b6a  jz      short loc_180017BA8
0x180017b6c  xor     edx, edx
0x180017b6e  lea     rcx, [rsp+838h+var_818]
0x180017b73  mov     word ptr [rsp+838h+var_818], dx
0x180017b78  mov     r8d, eax
0x180017b7b  lea     rdx, aRasupdateconne; "RasUpdateConnection failed with %!WINER"...
0x180017b82  call    FormatRRASErrorString
0x180017b87  test    cs:byte_1800AA941, 4
0x180017b8e  jz      short loc_180017BA8
0x180017b90  lea     r8, [rsp+838h+var_818]
0x180017b95  lea     rdx, RasVpnIkeTraceError
0x180017b9c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017ba3  call    McTemplateU0z_EventWriteTransfer
0x180017ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180017baf  cmp     rcx, r14
0x180017bb2  jz      short loc_180017BD8
0x180017bb4  test    byte ptr [rcx+1Ch], 1
0x180017bb8  jz      short loc_180017BD8
0x180017bba  cmp     byte ptr [rcx+19h], 2
0x180017bbe  jb      short loc_180017BD8
0x180017bc0  mov     rcx, [rcx+10h]
0x180017bc4  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180017bcb  mov     edx, 50h ; 'P'
0x180017bd0  mov     r9d, ebx
0x180017bd3  call    WPP_SF_d
0x180017bd8  mov     rcx, [rdi+8]; this
0x180017bdc  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x180017be1  call    cs:__imp_GetProcessHeap
0x180017be7  mov     r8, rdi; lpMem
0x180017bea  xor     edx, edx; dwFlags
0x180017bec  mov     rcx, rax; hHeap
0x180017bef  call    cs:__imp_HeapFree
0x180017bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bfc  cmp     rcx, r14
0x180017bff  jz      short loc_180017C25
0x180017c01  test    byte ptr [rcx+1Ch], 1
0x180017c05  jz      short loc_180017C25
0x180017c07  cmp     byte ptr [rcx+19h], 6
0x180017c0b  jb      short loc_180017C25
0x180017c0d  mov     rcx, [rcx+10h]
0x180017c11  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180017c18  mov     edx, 51h ; 'Q'
0x180017c1d  mov     r9d, ebx
0x180017c20  call    WPP_SF_d
0x180017c25  mov     eax, ebx
0x180017c27  mov     rcx, [rsp+838h+var_18]
0x180017c2f  xor     rcx, rsp; StackCookie
0x180017c32  call    __security_check_cookie
0x180017c37  lea     r11, [rsp+838h+var_8]
0x180017c3f  mov     rbx, [r11+10h]
0x180017c43  mov     rdi, [r11+20h]
0x180017c47  mov     rsp, r11
0x180017c4a  pop     r14
0x180017c4c  retn
```
