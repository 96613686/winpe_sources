# IpAllocationMgrCreate(in_addr,uchar,_IP_ALLOCATION_MGR * *)

- ea: `0x180075a68`
- end: `0x180075bfb`
- name: `?IpAllocationMgrCreate@@YAKUin_addr@@EPEAPEAU_IP_ALLOCATION_MGR@@@Z`
- size: `403`
- prototype: `unsigned int __fastcall(struct in_addr, unsigned __int8, struct _IP_ALLOCATION_MGR **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003c910`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c730`
- `0x18000e620`
- `0x180075a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180075b39`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180075b39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075b79`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075b79`

## pseudocode

```c
__int64 __fastcall IpAllocationMgrCreate(struct in_addr a1, unsigned __int8 a2, LPCRITICAL_SECTION *a3)
{
  PVOID *v6; // rcx
  unsigned int MSMSecMemory; // eax
  unsigned int v8; // esi
  int v9; // ebp
  struct _RTL_CRITICAL_SECTION *v10; // rax
  LPCRITICAL_SECTION v11; // rdi
  LPCRITICAL_SECTION v12; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp+18h] BYREF

  lpCriticalSection = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 && a2 <= 0x1Eu )
  {
    MSMSecMemory = AllocateMSMSecMemory(0x40u);
    v8 = MSMSecMemory;
    if ( MSMSecMemory )
    {
      v9 = 0;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
        v10 = lpCriticalSection;
        goto LABEL_13;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids, MSMSecMemory);
      v10 = lpCriticalSection;
    }
    else
    {
      v11 = lpCriticalSection;
      v12 = lpCriticalSection;
      *(_OWORD *)&lpCriticalSection->DebugInfo = 0;
      *(_OWORD *)&v12->OwningThread = 0;
      InitializeCriticalSection(v12);
      LODWORD(v11[1].DebugInfo) = a1;
      BYTE4(v11[1].DebugInfo) = a2;
      v9 = 1;
      v11[1].OwningThread = &v11[1].LockCount;
      *(_QWORD *)&v11[1].LockCount = (char *)v11 + 48;
      v10 = 0;
      lpCriticalSection = 0;
      *a3 = v11;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_13:
    if ( v10 )
    {
      if ( v9 )
        DeleteCriticalSection(v10);
      FreeMSMSecMemory(&lpCriticalSection);
      goto LABEL_20;
    }
    goto LABEL_21;
  }
  v8 = 87;
  if ( v6 == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)v6 + 68) & 1) != 0 )
  {
    WPP_SF_(v6[7], 21, &WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids);
LABEL_20:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_21:
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x100) != 0 )
    WPP_SF_d(v6[7], 23, &WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180075a68  mov     [rsp+arg_0], rbx
0x180075a6d  mov     [rsp+arg_8], rbp
0x180075a72  push    rsi
0x180075a73  push    rdi
0x180075a74  push    r12
0x180075a76  push    r14
0x180075a78  push    r15
0x180075a7a  sub     rsp, 20h
0x180075a7e  mov     r14, r8
0x180075a81  mov     [rsp+48h+lpCriticalSection], 0
0x180075a8a  mov     r15b, dl
0x180075a8d  mov     ebx, ecx
0x180075a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180075a96  lea     r12, WPP_GLOBAL_Control
0x180075a9d  cmp     rcx, r12
0x180075aa0  jz      short loc_180075AC7
0x180075aa2  test    dword ptr [rcx+44h], 100h
0x180075aa9  jz      short loc_180075AC7
0x180075aab  mov     rcx, [rcx+38h]
0x180075aaf  lea     r8, WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids
0x180075ab6  mov     edx, 14h
0x180075abb  call    WPP_SF_
0x180075ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180075ac7  test    r14, r14
0x180075aca  jz      loc_180075B91
0x180075ad0  cmp     r15b, 1Eh
0x180075ad4  ja      loc_180075B91
0x180075ada  lea     rdx, [rsp+48h+lpCriticalSection]
0x180075adf  mov     ecx, 40h ; '@'; dwBytes
0x180075ae4  call    AllocateMSMSecMemory
0x180075ae9  mov     esi, eax
0x180075aeb  test    eax, eax
0x180075aed  jz      short loc_180075B27
0x180075aef  xor     ebp, ebp
0x180075af1  mov     rcx, cs:WPP_GLOBAL_Control
0x180075af8  cmp     rcx, r12
0x180075afb  jz      short loc_180075B20
0x180075afd  test    byte ptr [rcx+44h], 1
0x180075b01  jz      short loc_180075B20
0x180075b03  mov     rcx, [rcx+38h]
0x180075b07  lea     edx, [rbp+16h]
0x180075b0a  mov     r9d, eax
0x180075b0d  lea     r8, WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids
0x180075b14  call    WPP_SF_d
0x180075b19  mov     rax, [rsp+48h+lpCriticalSection]
0x180075b1e  jmp     short loc_180075B66
0x180075b20  mov     rax, [rsp+48h+lpCriticalSection]
0x180075b25  jmp     short loc_180075B6D
0x180075b27  mov     rdi, [rsp+48h+lpCriticalSection]
0x180075b2c  xorps   xmm0, xmm0
0x180075b2f  mov     rcx, rdi; lpCriticalSection
0x180075b32  movups  xmmword ptr [rdi], xmm0
0x180075b35  movups  xmmword ptr [rdi+10h], xmm0
0x180075b39  call    cs:__imp_InitializeCriticalSection
0x180075b40  nop     dword ptr [rax+rax+00h]
0x180075b45  mov     [rdi+28h], ebx
0x180075b48  lea     rax, [rdi+30h]
0x180075b4c  mov     [rdi+2Ch], r15b
0x180075b50  mov     ebp, 1
0x180075b55  mov     [rax+8], rax
0x180075b59  mov     [rax], rax
0x180075b5c  xor     eax, eax
0x180075b5e  mov     [rsp+48h+lpCriticalSection], rax
0x180075b63  mov     [r14], rdi
0x180075b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180075b6d  test    rax, rax
0x180075b70  jz      short loc_180075BBB
0x180075b72  test    ebp, ebp
0x180075b74  jz      short loc_180075B85
0x180075b76  mov     rcx, rax; lpCriticalSection
0x180075b79  call    cs:__imp_DeleteCriticalSection
0x180075b80  nop     dword ptr [rax+rax+00h]
0x180075b85  lea     rcx, [rsp+48h+lpCriticalSection]
0x180075b8a  call    FreeMSMSecMemory
0x180075b8f  jmp     short loc_180075BB4
0x180075b91  mov     esi, 57h ; 'W'
0x180075b96  cmp     rcx, r12
0x180075b99  jz      short loc_180075BE1
0x180075b9b  test    byte ptr [rcx+44h], 1
0x180075b9f  jz      short loc_180075BBB
0x180075ba1  mov     rcx, [rcx+38h]
0x180075ba5  lea     edx, [rsi-42h]
0x180075ba8  lea     r8, WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids
0x180075baf  call    WPP_SF_
0x180075bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180075bbb  cmp     rcx, r12
0x180075bbe  jz      short loc_180075BE1
0x180075bc0  test    dword ptr [rcx+44h], 100h
0x180075bc7  jz      short loc_180075BE1
0x180075bc9  mov     rcx, [rcx+38h]
0x180075bcd  lea     r8, WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids
0x180075bd4  mov     edx, 17h
0x180075bd9  mov     r9d, esi
0x180075bdc  call    WPP_SF_d
0x180075be1  mov     rbx, [rsp+48h+arg_0]
0x180075be6  mov     eax, esi
0x180075be8  mov     rbp, [rsp+48h+arg_8]
0x180075bed  add     rsp, 20h
0x180075bf1  pop     r15
0x180075bf3  pop     r14
0x180075bf5  pop     r12
0x180075bf7  pop     rdi
0x180075bf8  pop     rsi
0x180075bf9  retn
```
