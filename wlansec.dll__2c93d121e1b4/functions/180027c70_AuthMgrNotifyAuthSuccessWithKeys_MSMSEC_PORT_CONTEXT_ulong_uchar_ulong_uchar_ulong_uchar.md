# AuthMgrNotifyAuthSuccessWithKeys(MSMSEC_PORT_CONTEXT *,ulong,uchar *,ulong,uchar *,ulong,uchar *)

- ea: `0x180027c70`
- end: `0x180027e97`
- name: `?AuthMgrNotifyAuthSuccessWithKeys@@YAKPEAUMSMSEC_PORT_CONTEXT@@KPEAEK1K1@Z`
- size: `551`
- prototype: `unsigned int(struct MSMSEC_PORT_CONTEXT *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180029660`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000b118`
- `0x18000c730`
- `0x18000d4bc`
- `0x1800197e8`
- `0x180027c70`
- `0x180044554`

## import_xrefs

- `OneX!OneXCopyAuthParams` at `0x180027ddd`
- `OneX!OneXCopyAuthParams` at `0x180027ddd`

## pseudocode

```c
__int64 __fastcall AuthMgrNotifyAuthSuccessWithKeys(
        struct MSMSEC_PORT_CONTEXT *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *Src,
        unsigned int a6,
        unsigned __int8 *a7)
{
  size_t v7; // r14
  size_t v9; // rsi
  unsigned int MSMSecMemory; // eax
  unsigned int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  void *v15; // rbx
  struct PORT_EVENT *v16; // rdi
  void *v17; // rbx
  struct PORT_EVENT *v19; // [rsp+20h] [rbp-20h] BYREF
  void *v20; // [rsp+28h] [rbp-18h]
  void *v21; // [rsp+30h] [rbp-10h]
  __int64 v22; // [rsp+38h] [rbp-8h] BYREF

  v7 = a4;
  v9 = a2;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 131, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
  MSMSecMemory = CreatePortEvent(10, 3, a1, &v19);
  v12 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_25;
    v14 = 132;
LABEL_24:
    WPP_SF_d(v13[7], v14, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, MSMSecMemory);
LABEL_25:
    DeletePortEvent(&v19);
    goto LABEL_26;
  }
  MSMSecMemory = AllocateMSMSecMemory((unsigned int)v9);
  v12 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_25;
    v14 = 133;
    goto LABEL_24;
  }
  v15 = v20;
  memcpy_0(v20, a3, v9);
  v16 = v19;
  *((_DWORD *)v19 + 10) = 4;
  *((_DWORD *)v16 + 11) = v9;
  *((_QWORD *)v16 + 6) = v15;
  MSMSecMemory = AllocateMSMSecMemory((unsigned int)v7);
  v12 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_25;
    v14 = 134;
    goto LABEL_24;
  }
  v17 = v21;
  memcpy_0(v21, Src, v7);
  *((_DWORD *)v16 + 14) = 4;
  *((_DWORD *)v16 + 15) = v7;
  *((_QWORD *)v16 + 8) = v17;
  MSMSecMemory = OneXCopyAuthParams(a6, a7, &v22);
  v12 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_25;
    v14 = 135;
    goto LABEL_24;
  }
  *((_DWORD *)v16 + 18) = 6;
  *((_DWORD *)v16 + 19) = a6;
  *((_QWORD *)v16 + 10) = v22;
  MSMSecMemory = QueuePublicPortEventInternal(v16, 1);
  v12 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_25;
    v14 = 136;
    goto LABEL_24;
  }
LABEL_26:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 137, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180027c70  push    rbp
0x180027c72  push    rbx
0x180027c73  push    rsi
0x180027c74  push    rdi
0x180027c75  push    r12
0x180027c77  push    r14
0x180027c79  push    r15
0x180027c7b  mov     rbp, rsp
0x180027c7e  sub     rsp, 40h
0x180027c82  mov     r14d, r9d
0x180027c85  mov     rdi, r8
0x180027c88  mov     esi, edx
0x180027c8a  mov     rbx, rcx
0x180027c8d  mov     [rbp+var_20], 0
0x180027c95  mov     [rbp+var_18], 0
0x180027c9d  mov     [rbp+var_10], 0
0x180027ca5  mov     [rbp+var_8], 0
0x180027cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cb4  lea     r15, WPP_GLOBAL_Control
0x180027cbb  lea     r12, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180027cc2  cmp     rcx, r15
0x180027cc5  jz      short loc_180027CE1
0x180027cc7  test    dword ptr [rcx+44h], 100h
0x180027cce  jz      short loc_180027CE1
0x180027cd0  mov     rcx, [rcx+38h]
0x180027cd4  mov     edx, 83h
0x180027cd9  mov     r8, r12
0x180027cdc  call    WPP_SF_
0x180027ce1  mov     edx, 3
0x180027ce6  lea     r9, [rbp+var_20]
0x180027cea  mov     r8, rbx
0x180027ced  lea     ecx, [rdx+7]
0x180027cf0  call    ?CreatePortEvent@@YAKW4MSMSEC_PORT_EVENT_TYPE@@KPEAXPEAPEAUPORT_EVENT@@@Z; CreatePortEvent(MSMSEC_PORT_EVENT_TYPE,ulong,void *,PORT_EVENT * *)
0x180027cf5  mov     ebx, eax
0x180027cf7  test    eax, eax
0x180027cf9  jz      short loc_180027D1F
0x180027cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d02  cmp     rcx, r15
0x180027d05  jz      loc_180027E53
0x180027d0b  test    byte ptr [rcx+44h], 1
0x180027d0f  jz      loc_180027E53
0x180027d15  mov     edx, 84h
0x180027d1a  jmp     loc_180027E44
0x180027d1f  lea     rdx, [rbp+var_18]
0x180027d23  mov     ecx, esi; dwBytes
0x180027d25  call    AllocateMSMSecMemory
0x180027d2a  mov     ebx, eax
0x180027d2c  test    eax, eax
0x180027d2e  jz      short loc_180027D54
0x180027d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d37  cmp     rcx, r15
0x180027d3a  jz      loc_180027E53
0x180027d40  test    byte ptr [rcx+44h], 1
0x180027d44  jz      loc_180027E53
0x180027d4a  mov     edx, 85h
0x180027d4f  jmp     loc_180027E44
0x180027d54  mov     rbx, [rbp+var_18]
0x180027d58  mov     r8, rsi; Size
0x180027d5b  mov     rcx, rbx; void *
0x180027d5e  mov     rdx, rdi; Src
0x180027d61  call    memcpy_0
0x180027d66  mov     rdi, [rbp+var_20]
0x180027d6a  lea     rdx, [rbp+var_10]
0x180027d6e  mov     ecx, r14d; dwBytes
0x180027d71  mov     dword ptr [rdi+28h], 4
0x180027d78  mov     [rdi+2Ch], esi
0x180027d7b  mov     [rdi+30h], rbx
0x180027d7f  call    AllocateMSMSecMemory
0x180027d84  mov     ebx, eax
0x180027d86  test    eax, eax
0x180027d88  jz      short loc_180027DAE
0x180027d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d91  cmp     rcx, r15
0x180027d94  jz      loc_180027E53
0x180027d9a  test    byte ptr [rcx+44h], 1
0x180027d9e  jz      loc_180027E53
0x180027da4  mov     edx, 86h
0x180027da9  jmp     loc_180027E44
0x180027dae  mov     rbx, [rbp+var_10]
0x180027db2  mov     r8, r14; Size
0x180027db5  mov     rdx, [rbp+Src]; Src
0x180027db9  mov     rcx, rbx; void *
0x180027dbc  call    memcpy_0
0x180027dc1  mov     esi, [rbp+arg_28]
0x180027dc4  lea     r8, [rbp+var_8]
0x180027dc8  mov     rdx, [rbp+arg_30]
0x180027dcc  mov     ecx, esi
0x180027dce  mov     dword ptr [rdi+38h], 4
0x180027dd5  mov     [rdi+3Ch], r14d
0x180027dd9  mov     [rdi+40h], rbx
0x180027ddd  call    cs:__imp_OneXCopyAuthParams
0x180027de4  nop     dword ptr [rax+rax+00h]
0x180027de9  mov     ebx, eax
0x180027deb  test    eax, eax
0x180027ded  jz      short loc_180027E08
0x180027def  mov     rcx, cs:WPP_GLOBAL_Control
0x180027df6  cmp     rcx, r15
0x180027df9  jz      short loc_180027E53
0x180027dfb  test    byte ptr [rcx+44h], 1
0x180027dff  jz      short loc_180027E53
0x180027e01  mov     edx, 87h
0x180027e06  jmp     short loc_180027E44
0x180027e08  mov     dword ptr [rdi+48h], 6
0x180027e0f  mov     edx, 1; int
0x180027e14  mov     [rdi+4Ch], esi
0x180027e17  mov     rcx, rdi; struct PORT_EVENT *
0x180027e1a  mov     rax, [rbp+var_8]
0x180027e1e  mov     [rdi+50h], rax
0x180027e22  call    ?QueuePublicPortEventInternal@@YAKPEAUPORT_EVENT@@H@Z; QueuePublicPortEventInternal(PORT_EVENT *,int)
0x180027e27  mov     ebx, eax
0x180027e29  test    eax, eax
0x180027e2b  jz      short loc_180027E5C
0x180027e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e34  cmp     rcx, r15
0x180027e37  jz      short loc_180027E53
0x180027e39  test    byte ptr [rcx+44h], 1
0x180027e3d  jz      short loc_180027E53
0x180027e3f  mov     edx, 88h
0x180027e44  mov     rcx, [rcx+38h]
0x180027e48  mov     r9d, eax
0x180027e4b  mov     r8, r12
0x180027e4e  call    WPP_SF_d
0x180027e53  lea     rcx, [rbp+var_20]; struct PORT_EVENT **
0x180027e57  call    ?DeletePortEvent@@YAKPEAPEAUPORT_EVENT@@@Z; DeletePortEvent(PORT_EVENT * *)
0x180027e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e63  cmp     rcx, r15
0x180027e66  jz      short loc_180027E85
0x180027e68  test    dword ptr [rcx+44h], 100h
0x180027e6f  jz      short loc_180027E85
0x180027e71  mov     rcx, [rcx+38h]
0x180027e75  mov     edx, 89h
0x180027e7a  mov     r9d, ebx
0x180027e7d  mov     r8, r12
0x180027e80  call    WPP_SF_d
0x180027e85  mov     eax, ebx
0x180027e87  add     rsp, 40h
0x180027e8b  pop     r15
0x180027e8d  pop     r14
0x180027e8f  pop     r12
0x180027e91  pop     rdi
0x180027e92  pop     rsi
0x180027e93  pop     rbx
0x180027e94  pop     rbp
0x180027e95  retn
```
