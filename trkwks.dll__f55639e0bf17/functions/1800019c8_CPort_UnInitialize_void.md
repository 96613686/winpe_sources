# CPort::UnInitialize(void)

- ea: `0x1800019c8`
- end: `0x180001b5e`
- name: `?UnInitialize@CPort@@QEAAXXZ`
- size: `406`
- prototype: `void __fastcall(CPort *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800016f4`
- `0x18000ef50`

## callees

- `0x1800019c8`
- `0x18000ed38`
- `0x180010fca`
- `0x180011000`

## import_xrefs

- `ntdll!NtAlpcConnectPort` at `0x180001ac4`
- `ntdll!NtAlpcConnectPort` at `0x180001ac4`
- `ntdll!RtlInitUnicodeString` at `0x180001a35`
- `ntdll!RtlInitUnicodeString` at `0x180001a35`
- `ntdll!NtClose` at `0x180001ad8`
- `ntdll!NtClose` at `0x180001b01`
- `ntdll!NtClose` at `0x180001b18`
- `ntdll!NtClose` at `0x180001b2f`
- `ntdll!NtClose` at `0x180001ad8`
- `ntdll!NtClose` at `0x180001b01`
- `ntdll!NtClose` at `0x180001b18`
- `ntdll!NtClose` at `0x180001b2f`

## string_xrefs

- `0x180001a12`: `\Security\TRKWKS_PORT`

## pseudocode

```c
void __fastcall CPort::UnInitialize(CPort *this)
{
  int v2; // ecx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  HANDLE Handle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v8; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v10[12]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v11[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v12; // [rsp+B4h] [rbp-4Ch]
  int v13; // [rsp+B8h] [rbp-48h]
  __int16 v14; // [rsp+BCh] [rbp-44h]
  __int64 v15; // [rsp+C0h] [rbp-40h]

  v2 = *((_DWORD *)this + 2);
  if ( (v2 & 1) != 0 )
  {
    Handle = 0;
    v8 = 48;
    *((_DWORD *)this + 2) = v2 | 2;
    memset(v10, 0, sizeof(v10));
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"\\Security\\TRKWKS_PORT");
    memset_0(v11, 0, 0x48u);
    v15 = 48;
    v12 = 12;
    v13 = 2;
    v14 = 257;
    v10[10] = 1;
    v10[0] = 2883588;
    if ( (int)NtAlpcConnectPort(&Handle, &DestinationString, 0, v11, 0x20000, 0, v10, &v8, 0, 0, 0) >= 0 && Handle )
      NtClose(Handle);
    v3 = (void *)*((_QWORD *)this + 2);
    if ( v3 )
      TrkUnregisterWait(v3, (void *)0xFFFFFFFFFFFFFFFFLL);
    v4 = (void *)*((_QWORD *)this + 4);
    *((_QWORD *)this + 2) = 0;
    if ( v4 )
      NtClose(v4);
    v5 = (void *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 4) = 0;
    if ( v5 )
      NtClose(v5);
    v6 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 3) = 0;
    if ( v6 )
      NtClose(v6);
    *((_DWORD *)this + 2) &= ~1u;
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x1800019c8  mov     [rsp-8+arg_8], rbx
0x1800019cd  push    rbp
0x1800019ce  lea     rbp, [rsp-10h]
0x1800019d3  sub     rsp, 110h
0x1800019da  mov     rax, cs:__security_cookie
0x1800019e1  xor     rax, rsp
0x1800019e4  mov     [rbp+10h+var_10], rax
0x1800019e8  mov     rbx, rcx
0x1800019eb  mov     ecx, [rcx+8]
0x1800019ee  test    cl, 1
0x1800019f1  jz      loc_180001B41
0x1800019f7  xorps   xmm0, xmm0
0x1800019fa  mov     [rsp+110h+Handle], 0
0x180001a03  or      ecx, 2
0x180001a06  mov     [rsp+110h+var_A8], 30h ; '0'
0x180001a0f  mov     [rbx+8], ecx
0x180001a12  lea     rdx, SourceString; "\\Security\\TRKWKS_PORT"
0x180001a19  xor     eax, eax
0x180001a1b  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x180001a20  movups  [rbp+10h+var_7E], xmm0
0x180001a24  mov     word ptr [rbp+10h+var_90], ax
0x180001a28  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x180001a2d  movups  xmmword ptr [rbp+10h+var_90+2], xmm0
0x180001a31  movups  [rbp+10h+var_7E+0Eh], xmm0
0x180001a35  call    cs:__imp_RtlInitUnicodeString
0x180001a3b  xor     edx, edx; Val
0x180001a3d  lea     rcx, [rbp+10h+var_60]; void *
0x180001a41  lea     r8d, [rdx+48h]; Size
0x180001a45  call    memset_0
0x180001a4a  mov     [rsp+110h+var_C0], 0
0x180001a53  lea     rax, [rsp+110h+var_A8]
0x180001a58  mov     [rsp+110h+var_C8], 0
0x180001a61  lea     r9, [rbp+10h+var_60]
0x180001a65  mov     [rsp+110h+var_D0], 0
0x180001a6e  lea     rdx, [rsp+110h+DestinationString]
0x180001a73  mov     [rsp+110h+var_D8], rax
0x180001a78  lea     rcx, [rsp+110h+Handle]
0x180001a7d  lea     rax, [rbp+10h+var_90]
0x180001a81  mov     [rbp+10h+var_50], 30h ; '0'
0x180001a89  mov     [rsp+110h+var_E0], rax
0x180001a8e  xor     r8d, r8d
0x180001a91  mov     [rsp+110h+var_E8], 0
0x180001a9a  mov     [rsp+110h+var_F0], 20000h
0x180001aa2  mov     [rbp+10h+var_5C], 0Ch
0x180001aa9  mov     [rbp+10h+var_58], 2
0x180001ab0  mov     [rbp+10h+var_54], 101h
0x180001ab6  mov     [rbp+10h+var_68], 1
0x180001abd  mov     dword ptr [rbp+10h+var_90], 2C0004h
0x180001ac4  call    cs:__imp_NtAlpcConnectPort
0x180001aca  test    eax, eax
0x180001acc  js      short loc_180001ADE
0x180001ace  mov     rcx, [rsp+110h+Handle]; Handle
0x180001ad3  test    rcx, rcx
0x180001ad6  jz      short loc_180001ADE
0x180001ad8  call    cs:__imp_NtClose
0x180001ade  mov     rcx, [rbx+10h]; void *
0x180001ae2  test    rcx, rcx
0x180001ae5  jz      short loc_180001AF0
0x180001ae7  or      rdx, 0FFFFFFFFFFFFFFFFh; void *
0x180001aeb  call    ?TrkUnregisterWait@@YAHPEAX0@Z; TrkUnregisterWait(void *,void *)
0x180001af0  mov     rcx, [rbx+20h]; Handle
0x180001af4  mov     qword ptr [rbx+10h], 0
0x180001afc  test    rcx, rcx
0x180001aff  jz      short loc_180001B07
0x180001b01  call    cs:__imp_NtClose
0x180001b07  mov     rcx, [rbx+18h]; Handle
0x180001b0b  mov     qword ptr [rbx+20h], 0
0x180001b13  test    rcx, rcx
0x180001b16  jz      short loc_180001B1E
0x180001b18  call    cs:__imp_NtClose
0x180001b1e  mov     rcx, [rbx+28h]; Handle
0x180001b22  mov     qword ptr [rbx+18h], 0
0x180001b2a  test    rcx, rcx
0x180001b2d  jz      short loc_180001B35
0x180001b2f  call    cs:__imp_NtClose
0x180001b35  and     dword ptr [rbx+8], 0FFFFFFFEh
0x180001b39  mov     qword ptr [rbx+28h], 0
0x180001b41  mov     rcx, [rbp+10h+var_10]
0x180001b45  xor     rcx, rsp; StackCookie
0x180001b48  call    __security_check_cookie
0x180001b4d  mov     rbx, [rsp+110h+arg_8]
0x180001b55  add     rsp, 110h
0x180001b5c  pop     rbp
0x180001b5d  retn
```
