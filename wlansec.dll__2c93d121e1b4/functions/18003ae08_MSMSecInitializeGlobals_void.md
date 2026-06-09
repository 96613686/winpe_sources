# MSMSecInitializeGlobals(void)

- ea: `0x18003ae08`
- end: `0x18003b06e`
- name: `?MSMSecInitializeGlobals@@YAKXZ`
- size: `614`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180050770`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180038b78`
- `0x18003ae08`
- `0x18003b284`
- `0x180040530`
- `0x180050a60`
- `0x180050c20`
- `0x18005c0fc`

## import_xrefs

- `MobileNetworking!CreateReadWriteLock` at `0x18003aeb5`
- `MobileNetworking!CreateReadWriteLock` at `0x18003aeb5`

## pseudocode

```c
__int64 MSMSecInitializeGlobals(void)
{
  int v0; // r14d
  int v1; // r15d
  int v2; // ebp
  PVOID *v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int v6; // esi
  unsigned int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx

  v0 = 0;
  v1 = 0;
  v2 = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 2) != 0 )
      WPP_SF_(v3[7], 35, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids);
  }
  qword_1800AF030 = (__int64)&qword_1800AF028;
  qword_1800AF028 = (__int64)&qword_1800AF028;
  qword_1800AF040 = (__int64)&qword_1800AF038;
  qword_1800AF038 = (__int64)&qword_1800AF038;
  MSMSecReadRegistryConfiguration();
  v4 = CreateReadWriteLock(qword_1800AEFC0);
  v5 = v4;
  if ( v4 )
  {
    v6 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 36, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v4);
    goto LABEL_11;
  }
  v6 = 1;
  v7 = MSMSecInitializeOneX();
  v5 = v7;
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_11;
    v9 = 37;
    goto LABEL_16;
  }
  v0 = 1;
  v7 = MSMSecInitializeTimers(&qword_1800AEF98);
  v5 = v7;
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_11;
    v9 = 38;
    goto LABEL_16;
  }
  v1 = 1;
  v7 = MSMSecInitializeAuthMgrHandleTable(&qword_1800AEFA8);
  v5 = v7;
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_11;
    v9 = 39;
    goto LABEL_16;
  }
  v7 = InitializeAuditing(&qword_1800AEFA0);
  v5 = v7;
  if ( !v7 )
  {
    qword_1800AEFB0 = 0;
    dword_1800AEFB8 = 0;
    goto LABEL_30;
  }
  v2 = 1;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v9 = 40;
LABEL_16:
    WPP_SF_d(v8[7], v9, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v7);
  }
LABEL_11:
  MSMSecDeinitializeHelper(v1, v0, v6, v2, 0);
LABEL_30:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18003ae08  push    rbx
0x18003ae0a  push    rbp
0x18003ae0b  push    rsi
0x18003ae0c  push    rdi
0x18003ae0d  push    r12
0x18003ae0f  push    r13
0x18003ae11  push    r14
0x18003ae13  push    r15
0x18003ae15  sub     rsp, 38h
0x18003ae19  xor     r13d, r13d
0x18003ae1c  mov     r14d, r13d
0x18003ae1f  mov     r15d, r13d
0x18003ae22  mov     ebp, r13d
0x18003ae25  mov     r12d, r13d
0x18003ae28  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae2f  lea     rdi, WPP_GLOBAL_Control
0x18003ae36  cmp     rcx, rdi
0x18003ae39  jz      short loc_18003AE7F
0x18003ae3b  test    dword ptr [rcx+44h], 100h
0x18003ae42  jz      short loc_18003AE5F
0x18003ae44  mov     rcx, [rcx+38h]
0x18003ae48  lea     edx, [r13+22h]
0x18003ae4c  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x18003ae53  call    WPP_SF_
0x18003ae58  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae5f  cmp     rcx, rdi
0x18003ae62  jz      short loc_18003AE7F
0x18003ae64  test    byte ptr [rcx+44h], 2
0x18003ae68  jz      short loc_18003AE7F
0x18003ae6a  mov     rcx, [rcx+38h]
0x18003ae6e  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x18003ae75  mov     edx, 23h ; '#'
0x18003ae7a  call    WPP_SF_
0x18003ae7f  lea     rax, qword_1800AF028
0x18003ae86  mov     cs:qword_1800AF030, rax
0x18003ae8d  mov     cs:qword_1800AF028, rax
0x18003ae94  lea     rax, qword_1800AF038
0x18003ae9b  mov     cs:qword_1800AF040, rax
0x18003aea2  mov     cs:qword_1800AF038, rax
0x18003aea9  call    ?MSMSecReadRegistryConfiguration@@YAXXZ; MSMSecReadRegistryConfiguration(void)
0x18003aeae  lea     rcx, qword_1800AEFC0
0x18003aeb5  call    cs:__imp_CreateReadWriteLock
0x18003aebc  nop     dword ptr [rax+rax+00h]
0x18003aec1  mov     ebx, eax
0x18003aec3  test    eax, eax
0x18003aec5  jz      short loc_18003AF19
0x18003aec7  mov     esi, r13d
0x18003aeca  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aed1  cmp     rcx, rdi
0x18003aed4  jz      short loc_18003AEF7
0x18003aed6  mov     edi, 1
0x18003aedb  test    [rcx+44h], dil
0x18003aedf  jz      short loc_18003AEF7
0x18003aee1  mov     rcx, [rcx+38h]
0x18003aee5  lea     edx, [rdi+23h]
0x18003aee8  mov     r9d, eax
0x18003aeeb  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x18003aef2  call    WPP_SF_d
0x18003aef7  lea     r13, WPP_GLOBAL_Control
0x18003aefe  mov     r9d, ebp; int
0x18003af01  mov     [rsp+78h+var_58], r12d; int
0x18003af06  mov     r8d, esi; int
0x18003af09  mov     edx, r14d; int
0x18003af0c  mov     ecx, r15d; int
0x18003af0f  call    ?MSMSecDeinitializeHelper@@YAXHHHHH@Z; MSMSecDeinitializeHelper(int,int,int,int,int)
0x18003af14  jmp     loc_18003B02D
0x18003af19  mov     edi, 1
0x18003af1e  mov     esi, edi
0x18003af20  call    ?MSMSecInitializeOneX@@YAKXZ; MSMSecInitializeOneX(void)
0x18003af25  mov     ebx, eax
0x18003af27  test    eax, eax
0x18003af29  jz      short loc_18003AF5C
0x18003af2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af32  lea     r13, WPP_GLOBAL_Control
0x18003af39  cmp     rcx, r13
0x18003af3c  jz      short loc_18003AEFE
0x18003af3e  test    [rcx+44h], dil
0x18003af42  jz      short loc_18003AEFE
0x18003af44  lea     edx, [rdi+24h]
0x18003af47  mov     rcx, [rcx+38h]
0x18003af4b  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x18003af52  mov     r9d, eax
0x18003af55  call    WPP_SF_d
0x18003af5a  jmp     short loc_18003AEFE
0x18003af5c  lea     rcx, qword_1800AEF98; void **
0x18003af63  mov     r14d, edi
0x18003af66  call    ?MSMSecInitializeTimers@@YAKPEAPEAX@Z; MSMSecInitializeTimers(void * *)
0x18003af6b  mov     ebx, eax
0x18003af6d  test    eax, eax
0x18003af6f  jz      short loc_18003AF99
0x18003af71  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af78  lea     r13, WPP_GLOBAL_Control
0x18003af7f  cmp     rcx, r13
0x18003af82  jz      loc_18003AEFE
0x18003af88  test    [rcx+44h], dil
0x18003af8c  jz      loc_18003AEFE
0x18003af92  mov     edx, 26h ; '&'
0x18003af97  jmp     short loc_18003AF47
0x18003af99  lea     rcx, qword_1800AEFA8; void **
0x18003afa0  mov     r15d, edi
0x18003afa3  call    ?MSMSecInitializeAuthMgrHandleTable@@YAKPEAPEAX@Z; MSMSecInitializeAuthMgrHandleTable(void * *)
0x18003afa8  mov     ebx, eax
0x18003afaa  test    eax, eax
0x18003afac  jz      short loc_18003AFD9
0x18003afae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003afb5  lea     r13, WPP_GLOBAL_Control
0x18003afbc  cmp     rcx, r13
0x18003afbf  jz      loc_18003AEFE
0x18003afc5  test    [rcx+44h], dil
0x18003afc9  jz      loc_18003AEFE
0x18003afcf  mov     edx, 27h ; '''
0x18003afd4  jmp     loc_18003AF47
0x18003afd9  lea     rcx, qword_1800AEFA0; struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ **
0x18003afe0  call    ?InitializeAuditing@@YAKPEAPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@@Z; InitializeAuditing(AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ * *)
0x18003afe5  mov     ebx, eax
0x18003afe7  test    eax, eax
0x18003afe9  jz      short loc_18003B018
0x18003afeb  mov     ebp, edi
0x18003afed  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aff4  lea     r13, WPP_GLOBAL_Control
0x18003affb  cmp     rcx, r13
0x18003affe  jz      loc_18003AEFE
0x18003b004  test    [rcx+44h], dil
0x18003b008  jz      loc_18003AEFE
0x18003b00e  mov     edx, 28h ; '('
0x18003b013  jmp     loc_18003AF47
0x18003b018  mov     cs:qword_1800AEFB0, r13
0x18003b01f  mov     cs:dword_1800AEFB8, r13d
0x18003b026  lea     r13, WPP_GLOBAL_Control
0x18003b02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b034  cmp     rcx, r13
0x18003b037  jz      short loc_18003B05A
0x18003b039  test    dword ptr [rcx+44h], 100h
0x18003b040  jz      short loc_18003B05A
0x18003b042  mov     rcx, [rcx+38h]
0x18003b046  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x18003b04d  mov     edx, 29h ; ')'
0x18003b052  mov     r9d, ebx
0x18003b055  call    WPP_SF_d
0x18003b05a  mov     eax, ebx
0x18003b05c  add     rsp, 38h
0x18003b060  pop     r15
0x18003b062  pop     r14
0x18003b064  pop     r13
0x18003b066  pop     r12
0x18003b068  pop     rdi
0x18003b069  pop     rsi
0x18003b06a  pop     rbp
0x18003b06b  pop     rbx
0x18003b06c  retn
```
