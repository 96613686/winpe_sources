# AuthMgrCreateOneXPort(_GUID *,ushort const *,ulong,void *,DOT11_MSMSEC_CONNECTION_PROFILE *,void * *)

- ea: `0x180036c98`
- end: `0x180036ef4`
- name: `?AuthMgrCreateOneXPort@@YAKPEAU_GUID@@PEBGKPEAXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAPEAX@Z`
- size: `604`
- prototype: `unsigned int __fastcall(struct _GUID *, const unsigned __int16 *, unsigned int, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000485c`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180036c98`
- `0x180043a30`
- `0x180044554`
- `0x18004456c`
- `0x1800445e4`
- `0x180094810`

## import_xrefs

- `OneX!OneXCreateSupplicantPort` at `0x180036e4d`
- `OneX!OneXCreateSupplicantPort` at `0x180036e4d`

## pseudocode

```c
__int64 __fastcall AuthMgrCreateOneXPort(
        struct _GUID *a1,
        const unsigned __int16 *a2,
        int a3,
        void *a4,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a5,
        void **a6)
{
  __int128 v10; // xmm0
  __int64 v11; // rbx
  unsigned int v12; // edi
  unsigned int v13; // eax
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  void *v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[2176]; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+8C0h] [rbp+7C0h] BYREF
  int v20; // [rsp+8C8h] [rbp+7C8h]
  __int128 v21; // [rsp+8CCh] [rbp+7CCh]
  wchar_t Buffer[1026]; // [rsp+8DCh] [rbp+7DCh] BYREF
  int v23; // [rsp+10E0h] [rbp+FE0h]
  __int64 (__fastcall *v24)(void *, void *, __int64, struct _ONEX_RESULT *); // [rsp+10E8h] [rbp+FE8h]
  unsigned int (__fastcall *v25)(void *, void *, size_t, unsigned __int8 *); // [rsp+10F0h] [rbp+FF0h]
  unsigned int (__fastcall *v26)(void *, void *); // [rsp+10F8h] [rbp+FF8h]
  __int64 (__fastcall *v27)(void *, void *, SIZE_T, void *); // [rsp+1100h] [rbp+1000h]
  __int64 (__fastcall *v28)(void *, void *, void *, SIZE_T, void *); // [rsp+1108h] [rbp+1008h]
  __int64 (__fastcall *v29)(void *, void *, void *, unsigned int *, void **); // [rsp+1110h] [rbp+1010h]
  unsigned int (__fastcall *v30)(void *); // [rsp+1118h] [rbp+1018h]
  unsigned int (__usercall *v31)@<eax>(void *@<rcx>, void *@<rdx>, unsigned int@<r8d>, int@<r9d>, unsigned int, void *); // [rsp+1120h] [rbp+1020h]
  __int64 (__fastcall *v32)(void *, void *, struct _L2_NOTIFICATION_DATA *); // [rsp+1128h] [rbp+1028h]
  unsigned int (__fastcall *v33)(void *, void *, unsigned int, void *); // [rsp+1130h] [rbp+1030h]
  __int64 (__fastcall *v34)(void *, void *, unsigned int *, void **); // [rsp+1138h] [rbp+1038h]

  v17 = 0;
  memset_0(&Src, 0, 0x880u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  v10 = (__int128)*a1;
  v11 = *((_QWORD *)a5 + 6);
  v12 = *((_DWORD *)a5 + 10);
  Src = a4;
  v20 = 0;
  v21 = v10;
  v23 = a3;
  swprintf_s(Buffer, 0x401u, L"%s", a2);
  v32 = AuthMgrOneXNotify;
  v30 = AuthMgrOneXFree;
  v29 = AuthMgrOneXQueryUserProfile;
  v25 = AuthMgrOneXSendPacket;
  v27 = AuthMgrOneXSetConnectionProfile;
  v28 = AuthMgrOneXSetUserProfile;
  v31 = AuthMgrOneXUIRequest;
  v24 = AuthMgrOneXUpdateResult;
  v33 = AuthMgrOneXUpdateAuthParams;
  v26 = AuthMgrOneXDestroyPortCompletion;
  v34 = AuthMgrOneXQueryParams;
  memcpy_0(v18, &Src, sizeof(v18));
  v13 = OneXCreateSupplicantPort(1, v18, v12, v11, &v17, 0);
  v14 = v13;
  if ( !v13 )
  {
    *a6 = v17;
    goto LABEL_9;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v13);
LABEL_9:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 17) & 0x100) != 0 )
    WPP_SF_d(v15[7], 14, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180036c98  push    rbp
0x180036c9a  push    rbx
0x180036c9b  push    rsi
0x180036c9c  push    rdi
0x180036c9d  push    r12
0x180036c9f  push    r13
0x180036ca1  push    r14
0x180036ca3  push    r15
0x180036ca5  lea     rbp, [rsp-1058h]
0x180036cad  mov     eax, 1158h
0x180036cb2  call    _alloca_probe
0x180036cb7  sub     rsp, rax
0x180036cba  mov     rax, cs:__security_cookie
0x180036cc1  xor     rax, rsp
0x180036cc4  mov     [rbp+1090h+var_50], rax
0x180036ccb  mov     rdi, [rbp+1090h+arg_20]
0x180036cd2  mov     r12d, r8d
0x180036cd5  mov     rsi, [rbp+1090h+arg_28]
0x180036cdc  mov     r15, rdx
0x180036cdf  mov     r14, rcx
0x180036ce2  mov     [rsp+1190h+var_1160], 0
0x180036ceb  xor     edx, edx; Val
0x180036ced  lea     rcx, [rbp+1090h+Src]; void *
0x180036cf4  mov     r8d, 880h; Size
0x180036cfa  mov     r13, r9
0x180036cfd  call    memset_0
0x180036d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d09  lea     rax, WPP_GLOBAL_Control
0x180036d10  cmp     rcx, rax
0x180036d13  jz      short loc_180036D33
0x180036d15  test    dword ptr [rcx+44h], 100h
0x180036d1c  jz      short loc_180036D33
0x180036d1e  mov     rcx, [rcx+38h]
0x180036d22  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180036d29  mov     edx, 0Ch
0x180036d2e  call    WPP_SF_
0x180036d33  movups  xmm0, xmmword ptr [r14]
0x180036d37  mov     rbx, [rdi+30h]
0x180036d3b  lea     r8, aS_0; "%s"
0x180036d42  mov     edi, [rdi+28h]
0x180036d45  lea     rcx, [rbp+1090h+Buffer]; Buffer
0x180036d4c  mov     r9, r15
0x180036d4f  mov     [rbp+1090h+Src], r13
0x180036d56  mov     edx, 401h; BufferCount
0x180036d5b  mov     [rbp+1090h+var_8C8], 0
0x180036d65  movdqu  [rbp+1090h+var_8C4], xmm0
0x180036d6d  mov     [rbp+1090h+var_B0], r12d
0x180036d74  call    swprintf_s
0x180036d79  lea     rax, ?AuthMgrOneXNotify@@YAKPEAX0PEAU_L2_NOTIFICATION_DATA@@@Z; AuthMgrOneXNotify(void *,void *,_L2_NOTIFICATION_DATA *)
0x180036d80  mov     r8d, 880h; Size
0x180036d86  mov     [rbp+1090h+var_68], rax
0x180036d8d  lea     rcx, [rsp+1190h+var_1150]; void *
0x180036d92  lea     rax, ?AuthMgrOneXFree@@YAKPEAX@Z; AuthMgrOneXFree(void *)
0x180036d99  mov     [rbp+1090h+var_78], rax
0x180036da0  lea     rdx, [rbp+1090h+Src]; Src
0x180036da7  lea     rax, ?AuthMgrOneXQueryUserProfile@@YAKPEAX00PEAKPEAPEAX@Z; AuthMgrOneXQueryUserProfile(void *,void *,void *,ulong *,void * *)
0x180036dae  mov     [rbp+1090h+var_80], rax
0x180036db5  lea     rax, ?AuthMgrOneXSendPacket@@YAKPEAX0KPEAE@Z; AuthMgrOneXSendPacket(void *,void *,ulong,uchar *)
0x180036dbc  mov     [rbp+1090h+var_A0], rax
0x180036dc3  lea     rax, ?AuthMgrOneXSetConnectionProfile@@YAKPEAX0K0@Z; AuthMgrOneXSetConnectionProfile(void *,void *,ulong,void *)
0x180036dca  mov     [rbp+1090h+var_90], rax
0x180036dd1  lea     rax, ?AuthMgrOneXSetUserProfile@@YAKPEAX00K0@Z; AuthMgrOneXSetUserProfile(void *,void *,void *,ulong,void *)
0x180036dd8  mov     [rbp+1090h+var_88], rax
0x180036ddf  lea     rax, ?AuthMgrOneXUIRequest@@YAKPEAX0KHK0@Z; AuthMgrOneXUIRequest(void *,void *,ulong,int,ulong,void *)
0x180036de6  mov     [rbp+1090h+var_70], rax
0x180036ded  lea     rax, ?AuthMgrOneXUpdateResult@@YAKPEAX0KPEAU_ONEX_RESULT@@@Z; AuthMgrOneXUpdateResult(void *,void *,ulong,_ONEX_RESULT *)
0x180036df4  mov     [rbp+1090h+var_A8], rax
0x180036dfb  lea     rax, ?AuthMgrOneXUpdateAuthParams@@YAKPEAX0K0@Z; AuthMgrOneXUpdateAuthParams(void *,void *,ulong,void *)
0x180036e02  mov     [rbp+1090h+var_60], rax
0x180036e09  lea     rax, ?AuthMgrOneXDestroyPortCompletion@@YAKPEAX0@Z; AuthMgrOneXDestroyPortCompletion(void *,void *)
0x180036e10  mov     [rbp+1090h+var_98], rax
0x180036e17  lea     rax, ?AuthMgrOneXQueryParams@@YAKPEAX0PEAKPEAPEAX@Z; AuthMgrOneXQueryParams(void *,void *,ulong *,void * *)
0x180036e1e  mov     [rbp+1090h+var_58], rax
0x180036e25  call    memcpy_0
0x180036e2a  lea     rax, [rsp+1190h+var_1160]
0x180036e2f  mov     [rsp+1190h+var_1168], 0
0x180036e38  mov     r9, rbx
0x180036e3b  mov     [rsp+1190h+var_1170], rax
0x180036e40  mov     r8d, edi
0x180036e43  lea     rdx, [rsp+1190h+var_1150]
0x180036e48  mov     ecx, 1
0x180036e4d  call    cs:__imp_OneXCreateSupplicantPort
0x180036e54  nop     dword ptr [rax+rax+00h]
0x180036e59  mov     ebx, eax
0x180036e5b  test    eax, eax
0x180036e5d  jz      short loc_180036E92
0x180036e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e66  lea     rdi, WPP_GLOBAL_Control
0x180036e6d  cmp     rcx, rdi
0x180036e70  jz      short loc_180036ECE
0x180036e72  test    byte ptr [rcx+44h], 1
0x180036e76  jz      short loc_180036EA8
0x180036e78  mov     rcx, [rcx+38h]
0x180036e7c  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180036e83  mov     edx, 0Dh
0x180036e88  mov     r9d, eax
0x180036e8b  call    WPP_SF_d
0x180036e90  jmp     short loc_180036EA1
0x180036e92  mov     rax, [rsp+1190h+var_1160]
0x180036e97  lea     rdi, WPP_GLOBAL_Control
0x180036e9e  mov     [rsi], rax
0x180036ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ea8  cmp     rcx, rdi
0x180036eab  jz      short loc_180036ECE
0x180036ead  test    dword ptr [rcx+44h], 100h
0x180036eb4  jz      short loc_180036ECE
0x180036eb6  mov     rcx, [rcx+38h]
0x180036eba  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180036ec1  mov     edx, 0Eh
0x180036ec6  mov     r9d, ebx
0x180036ec9  call    WPP_SF_d
0x180036ece  mov     eax, ebx
0x180036ed0  mov     rcx, [rbp+1090h+var_50]
0x180036ed7  xor     rcx, rsp; StackCookie
0x180036eda  call    __security_check_cookie
0x180036edf  add     rsp, 1158h
0x180036ee6  pop     r15
0x180036ee8  pop     r14
0x180036eea  pop     r13
0x180036eec  pop     r12
0x180036eee  pop     rdi
0x180036eef  pop     rsi
0x180036ef0  pop     rbx
0x180036ef1  pop     rbp
0x180036ef2  retn
```
