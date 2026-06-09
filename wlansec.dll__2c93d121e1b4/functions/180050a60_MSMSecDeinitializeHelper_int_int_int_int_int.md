# MSMSecDeinitializeHelper(int,int,int,int,int)

- ea: `0x180050a60`
- end: `0x180050c17`
- name: `?MSMSecDeinitializeHelper@@YAXHHHHH@Z`
- size: `439`
- prototype: `void __fastcall(int, int, int, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003ae08`
- `0x1800508e0`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180050a60`
- `0x18005c004`
- `0x1800738ec`

## import_xrefs

- `MobileNetworking!L2DeinitializeAuditing` at `0x180050ba8`
- `MobileNetworking!L2DeinitializeAuditing` at `0x180050ba8`
- `MobileNetworking!HtDestroyHandleTable` at `0x180050b59`
- `MobileNetworking!HtDestroyHandleTable` at `0x180050b59`
- `MobileNetworking!DeleteReadWriteLock` at `0x180050b3b`
- `MobileNetworking!DeleteReadWriteLock` at `0x180050b3b`

## pseudocode

```c
void __fastcall MSMSecDeinitializeHelper(int a1, int a2, int a3, int a4, int a5)
{
  PVOID *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v10 = MSMSecDeinitializeTimers(&qword_1800AEF98);
    if ( !v10 )
    {
LABEL_9:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_10;
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v10);
      goto LABEL_9;
    }
  }
LABEL_10:
  if ( !a2 )
    goto LABEL_16;
  v11 = MSMSecDeinitializeOneX();
  if ( !v11 )
    goto LABEL_15;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v11);
LABEL_15:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_16:
  if ( a3 )
  {
    DeleteReadWriteLock(qword_1800AEFC0);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    HtDestroyHandleTable(qword_1800AEFA8);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    qword_1800AEFA8 = 0;
  }
  if ( a5 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
      WPP_SF_(v9[7], 13, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids);
    L2DeinitializeAuditing(&qword_1800AEFA0);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  qword_1800AF030 = (__int64)&qword_1800AF028;
  qword_1800AF028 = (__int64)&qword_1800AF028;
  qword_1800AF040 = (__int64)&qword_1800AF038;
  qword_1800AF038 = (__int64)&qword_1800AF038;
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
    WPP_SF_d(v9[7], 30, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, 0);
}

```

## disassembly

```asm
0x180050a60  push    rbx
0x180050a62  push    rbp
0x180050a63  push    rsi
0x180050a64  push    rdi
0x180050a65  push    r14
0x180050a67  sub     rsp, 20h
0x180050a6b  mov     ebp, r9d
0x180050a6e  mov     esi, r8d
0x180050a71  mov     edi, edx
0x180050a73  mov     ebx, ecx
0x180050a75  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a7c  lea     r14, WPP_GLOBAL_Control
0x180050a83  cmp     rcx, r14
0x180050a86  jz      short loc_180050AAD
0x180050a88  test    dword ptr [rcx+44h], 100h
0x180050a8f  jz      short loc_180050AAD
0x180050a91  mov     rcx, [rcx+38h]
0x180050a95  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180050a9c  mov     edx, 1Bh
0x180050aa1  call    WPP_SF_
0x180050aa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180050aad  test    ebx, ebx
0x180050aaf  jz      short loc_180050AF2
0x180050ab1  lea     rcx, qword_1800AEF98; void **
0x180050ab8  call    ?MSMSecDeinitializeTimers@@YAKPEAPEAX@Z; MSMSecDeinitializeTimers(void * *)
0x180050abd  test    eax, eax
0x180050abf  jz      short loc_180050AEB
0x180050ac1  mov     rcx, cs:WPP_GLOBAL_Control
0x180050ac8  cmp     rcx, r14
0x180050acb  jz      short loc_180050AF2
0x180050acd  test    byte ptr [rcx+44h], 1
0x180050ad1  jz      short loc_180050AF2
0x180050ad3  mov     rcx, [rcx+38h]
0x180050ad7  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180050ade  mov     edx, 1Ch
0x180050ae3  mov     r9d, eax
0x180050ae6  call    WPP_SF_d
0x180050aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180050af2  test    edi, edi
0x180050af4  jz      short loc_180050B30
0x180050af6  call    ?MSMSecDeinitializeOneX@@YAKXZ; MSMSecDeinitializeOneX(void)
0x180050afb  test    eax, eax
0x180050afd  jz      short loc_180050B29
0x180050aff  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b06  cmp     rcx, r14
0x180050b09  jz      short loc_180050B30
0x180050b0b  test    byte ptr [rcx+44h], 1
0x180050b0f  jz      short loc_180050B30
0x180050b11  mov     rcx, [rcx+38h]
0x180050b15  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180050b1c  mov     edx, 1Dh
0x180050b21  mov     r9d, eax
0x180050b24  call    WPP_SF_d
0x180050b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b30  test    esi, esi
0x180050b32  jz      short loc_180050B4E
0x180050b34  lea     rcx, qword_1800AEFC0
0x180050b3b  call    cs:__imp_DeleteReadWriteLock
0x180050b42  nop     dword ptr [rax+rax+00h]
0x180050b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b4e  test    ebp, ebp
0x180050b50  jz      short loc_180050B77
0x180050b52  mov     rcx, cs:qword_1800AEFA8
0x180050b59  call    cs:__imp_HtDestroyHandleTable
0x180050b60  nop     dword ptr [rax+rax+00h]
0x180050b65  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b6c  mov     cs:qword_1800AEFA8, 0
0x180050b77  cmp     [rsp+48h+arg_20], 0
0x180050b7c  jz      short loc_180050BBB
0x180050b7e  cmp     rcx, r14
0x180050b81  jz      short loc_180050BA1
0x180050b83  test    dword ptr [rcx+44h], 100h
0x180050b8a  jz      short loc_180050BA1
0x180050b8c  mov     rcx, [rcx+38h]
0x180050b90  lea     r8, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids
0x180050b97  mov     edx, 0Dh
0x180050b9c  call    WPP_SF_
0x180050ba1  lea     rcx, qword_1800AEFA0
0x180050ba8  call    cs:__imp_L2DeinitializeAuditing
0x180050baf  nop     dword ptr [rax+rax+00h]
0x180050bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180050bbb  lea     rax, qword_1800AF028
0x180050bc2  mov     cs:qword_1800AF030, rax
0x180050bc9  mov     cs:qword_1800AF028, rax
0x180050bd0  lea     rax, qword_1800AF038
0x180050bd7  mov     cs:qword_1800AF040, rax
0x180050bde  mov     cs:qword_1800AF038, rax
0x180050be5  cmp     rcx, r14
0x180050be8  jz      short loc_180050C0B
0x180050bea  test    dword ptr [rcx+44h], 100h
0x180050bf1  jz      short loc_180050C0B
0x180050bf3  mov     rcx, [rcx+38h]
0x180050bf7  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180050bfe  mov     edx, 1Eh
0x180050c03  xor     r9d, r9d
0x180050c06  call    WPP_SF_d
0x180050c0b  add     rsp, 20h
0x180050c0f  pop     r14
0x180050c11  pop     rdi
0x180050c12  pop     rsi
0x180050c13  pop     rbp
0x180050c14  pop     rbx
0x180050c15  retn
```
