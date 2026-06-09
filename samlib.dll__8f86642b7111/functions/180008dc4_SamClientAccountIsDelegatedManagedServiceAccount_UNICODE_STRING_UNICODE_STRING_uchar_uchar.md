# SamClientAccountIsDelegatedManagedServiceAccount(_UNICODE_STRING *,_UNICODE_STRING *,uchar *,uchar *)

- ea: `0x180008dc4`
- end: `0x180008f56`
- name: `?SamClientAccountIsDelegatedManagedServiceAccount@@YAJPEAU_UNICODE_STRING@@0PEAE1@Z`
- size: `402`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012790`

## callees

- `0x180001800`
- `0x180004dd0`
- `0x18000807c`
- `0x180008dc4`
- `0x18001461c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180008e8d`
- `RPCRT4!NdrClientCall3` at `0x180008e8d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180008ed0`
- `RPCRT4!I_RpcMapWin32Status` at `0x180008ed0`

## pseudocode

```c
__int64 __fastcall SamClientAccountIsDelegatedManagedServiceAccount(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  int v7; // r15d
  int v8; // eax
  int Pointer; // ebx
  _QWORD *v10; // rcx
  CLIENT_CALL_RETURN v11; // rax
  unsigned __int8 v13; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int8 v14[3]; // [rsp+41h] [rbp-37h] BYREF
  int v15; // [rsp+44h] [rbp-34h]
  void *v16; // [rsp+48h] [rbp-30h] BYREF
  CLIENT_CALL_RETURN v17; // [rsp+50h] [rbp-28h]

  v7 = (int)a1;
  v16 = 0;
  v13 = 0;
  v14[0] = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = SamConnect(a1, (__int64 *)&v16, 32);
  Pointer = v8;
  v10 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ZD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      392,
      (unsigned int)&WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
      v7,
      v8);
    v10 = WPP_GLOBAL_Control;
  }
  if ( Pointer >= 0 )
  {
    v17.Simple = 0;
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x4Du, 0, *(_QWORD *)v16, a2, &v13, v14).Pointer;
    Pointer = (int)v11.Pointer;
    v17.Pointer = v11.Pointer;
    v15 = (int)v11.Pointer;
    *a3 = v13;
    *a4 = v14[0];
    v10 = WPP_GLOBAL_Control;
  }
  if ( v16 )
  {
    SamCloseHandle(v16);
    v10 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_D(v10[2], 394, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, (unsigned int)Pointer);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180008dc4  mov     rax, rsp
0x180008dc7  mov     [rax+8], rbx
0x180008dcb  mov     [rax+10h], rsi
0x180008dcf  mov     [rax+20h], r9
0x180008dd3  mov     [rax+18h], r8
0x180008dd7  push    r12
0x180008dd9  push    r14
0x180008ddb  push    r15
0x180008ddd  sub     rsp, 60h
0x180008de1  mov     rsi, r9
0x180008de4  mov     r14, r8
0x180008de7  mov     r12, rdx
0x180008dea  mov     r15, rcx
0x180008ded  mov     qword ptr [rax-30h], 0
0x180008df5  mov     byte ptr [rax-38h], 0
0x180008df9  mov     byte ptr [rax-37h], 0
0x180008dfd  mov     byte ptr [r8], 0
0x180008e01  mov     byte ptr [r9], 0
0x180008e05  xor     r9d, r9d
0x180008e08  lea     r8d, [r9+20h]
0x180008e0c  lea     rdx, [rax-30h]
0x180008e10  call    SamConnect
0x180008e15  mov     ebx, eax
0x180008e17  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e1e  test    byte ptr [rcx+1Ch], 2
0x180008e22  jz      short loc_180008E4D
0x180008e24  cmp     byte ptr [rcx+19h], 4
0x180008e28  jb      short loc_180008E4D
0x180008e2a  mov     edx, 188h
0x180008e2f  mov     dword ptr [rsp+78h+var_58], eax
0x180008e33  mov     r9, r15
0x180008e36  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180008e3d  mov     rcx, [rcx+10h]
0x180008e41  call    WPP_SF_ZD
0x180008e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e4d  test    ebx, ebx
0x180008e4f  js      loc_180008F00
0x180008e55  mov     rax, [rsp+78h+var_30]
0x180008e5a  mov     [rsp+78h+var_28], 0
0x180008e63  lea     rcx, [rsp+78h+var_37]
0x180008e68  mov     [rsp+78h+var_48], rcx
0x180008e6d  lea     rcx, [rsp+78h+var_38]
0x180008e72  mov     [rsp+78h+var_50], rcx
0x180008e77  mov     [rsp+78h+var_58], r12
0x180008e7c  mov     r9, [rax]
0x180008e7f  xor     r8d, r8d; pReturnValue
0x180008e82  lea     edx, [r8+4Dh]; nProcNum
0x180008e86  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180008e8d  call    cs:__imp_NdrClientCall3
0x180008e93  mov     rbx, rax
0x180008e96  mov     [rsp+78h+var_28], rax
0x180008e9b  mov     [rsp+78h+var_34], eax
0x180008e9f  jmp     short loc_180008EEC
0x180008ea1  mov     ebx, eax
0x180008ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008eaa  test    byte ptr [rcx+1Ch], 2
0x180008eae  jz      short loc_180008ECE
0x180008eb0  cmp     byte ptr [rcx+19h], 3
0x180008eb4  jb      short loc_180008ECE
0x180008eb6  mov     r9d, eax
0x180008eb9  mov     edx, 189h
0x180008ebe  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180008ec5  mov     rcx, [rcx+10h]
0x180008ec9  call    WPP_SF_D
0x180008ece  mov     ecx, ebx; Status
0x180008ed0  call    cs:__imp_I_RpcMapWin32Status
0x180008ed6  mov     ebx, eax
0x180008ed8  mov     [rsp+78h+var_34], eax
0x180008edc  mov     rsi, [rsp+78h+arg_18]
0x180008ee4  mov     r14, [rsp+78h+arg_10]
0x180008eec  mov     al, [rsp+78h+var_38]
0x180008ef0  mov     [r14], al
0x180008ef3  mov     al, [rsp+78h+var_37]
0x180008ef7  mov     [rsi], al
0x180008ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f00  cmp     [rsp+78h+var_30], 0
0x180008f06  jz      short loc_180008F19
0x180008f08  mov     rcx, [rsp+78h+var_30]; void *
0x180008f0d  call    SamCloseHandle
0x180008f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f19  test    byte ptr [rcx+1Ch], 2
0x180008f1d  jz      short loc_180008F3D
0x180008f1f  cmp     byte ptr [rcx+19h], 4
0x180008f23  jb      short loc_180008F3D
0x180008f25  mov     edx, 18Ah
0x180008f2a  mov     r9d, ebx
0x180008f2d  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180008f34  mov     rcx, [rcx+10h]
0x180008f38  call    WPP_SF_D
0x180008f3d  mov     eax, ebx
0x180008f3f  lea     r11, [rsp+78h+var_18]
0x180008f44  mov     rbx, [r11+20h]
0x180008f48  mov     rsi, [r11+28h]
0x180008f4c  mov     rsp, r11
0x180008f4f  pop     r15
0x180008f51  pop     r14
0x180008f53  pop     r12
0x180008f55  retn
0x180017cf0  push    rbp
0x180017cf2  sub     rsp, 40h
0x180017cf6  mov     rbp, rdx
0x180017cf9  mov     rcx, [rcx]
0x180017cfc  mov     ecx, [rcx]; ExceptionCode
0x180017cfe  call    cs:__imp_I_RpcExceptionFilter
0x180017d04  nop
0x180017d05  add     rsp, 40h
0x180017d09  pop     rbp
0x180017d0a  retn
```
