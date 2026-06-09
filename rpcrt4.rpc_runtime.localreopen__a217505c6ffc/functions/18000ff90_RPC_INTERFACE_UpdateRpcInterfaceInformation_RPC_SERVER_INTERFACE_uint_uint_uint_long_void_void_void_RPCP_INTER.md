# RPC_INTERFACE::UpdateRpcInterfaceInformation(_RPC_SERVER_INTERFACE *,uint,uint,uint,long (*)(void *,void *),void *,RPCP_INTERFACE_GROUP *)

- ea: `0x18000ff90`
- end: `0x18001023d`
- name: `?UpdateRpcInterfaceInformation@RPC_INTERFACE@@QEAAJPEAU_RPC_SERVER_INTERFACE@@IIIP6AJPEAX1@Z1PEAVRPCP_INTERFACE_GROUP@@@Z`
- size: `685`
- prototype: `__int64 __fastcall(RPC_INTERFACE *this, struct _RPC_SERVER_INTERFACE *, int, int, unsigned int, int (*)(void *, void *), PSECURITY_DESCRIPTOR CreatorDescriptor, struct RPCP_INTERFACE_GROUP *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000f110`
- `0x1800900a0`

## callees

- `0x18000ff90`
- `0x180010244`
- `0x180023020`
- `0x180023a40`
- `0x18002cab0`
- `0x1800cec85`
- `0x1800cec91`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800101d6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800101eb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800101d6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800101eb`

## pseudocode

```c
__int64 __fastcall RPC_INTERFACE::UpdateRpcInterfaceInformation(
        RPC_INTERFACE *this,
        struct _RPC_SERVER_INTERFACE *a2,
        int a3,
        int a4,
        unsigned int a5,
        int (*a6)(void *, void *),
        PSECURITY_DESCRIPTOR CreatorDescriptor,
        struct RPCP_INTERFACE_GROUP *a8)
{
  size_t Length; // r15
  void *v9; // rsi
  unsigned int v14; // eax
  unsigned int v15; // edi
  _DWORD *InterpreterInfo; // rcx
  int v17; // eax
  void *v18; // rcx
  void *v19; // rax
  __int64 i; // r10
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // r9
  void *v25; // rcx
  unsigned int v26; // eax
  bool v27; // cf
  __int64 v28; // rcx
  REFERENCED_OBJECT *v29; // rcx
  DWORD SecurityDescriptorLength; // edi
  void *lpMem; // [rsp+58h] [rbp+10h] BYREF

  Length = a2->Length;
  v9 = 0;
  lpMem = 0;
  if ( (((_DWORD)Length - 64) & 0xFFFFFFDF) != 0 )
    return 1717;
  if ( CreatorDescriptor )
  {
    v14 = RpcpNormalizeSecurityDescriptor(CreatorDescriptor, 0, &lpMem);
    v9 = lpMem;
    v15 = v14;
    if ( v14 )
      goto LABEL_21;
  }
  if ( *((_DWORD *)this + 50) )
  {
    if ( *((_DWORD *)this + 2) == a3 && *((int (**)(void *, void *))this + 9) == a6 )
    {
      if ( v9 )
      {
LABEL_32:
        if ( !*((_QWORD *)this + 70) )
          goto LABEL_35;
        SecurityDescriptorLength = GetSecurityDescriptorLength(v9);
        if ( SecurityDescriptorLength != GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)this + 70))
          || memcmp_0(v9, *((const void **)this + 70), SecurityDescriptorLength) )
        {
          goto LABEL_35;
        }
LABEL_15:
        v26 = a5;
        v27 = a5 < 0x7FFFFFFF;
        *((_DWORD *)this + 51) = a4;
        if ( !v27 )
          v26 = 0x7FFFFFFF;
        ++*((_DWORD *)this + 91);
        v28 = *((_QWORD *)this + 71);
        v15 = 0;
        *((_DWORD *)this + 82) = v26;
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 32LL))(v28);
        v29 = a8;
        *((_QWORD *)this + 71) = a8;
        if ( v29 )
          REFERENCED_OBJECT::AddReference(v29);
        goto LABEL_21;
      }
      if ( !*((_QWORD *)this + 70) )
        goto LABEL_15;
    }
    if ( !v9 )
    {
LABEL_35:
      v15 = 87;
      goto LABEL_21;
    }
    goto LABEL_32;
  }
  if ( (a2->Flags & 0x2000000) == 0 )
  {
    *((_DWORD *)this + 48) = 0;
LABEL_11:
    memcpy_0((char *)this + 80, a2, Length);
    *((_DWORD *)this + 2) = 0;
    v25 = (void *)*((_QWORD *)this + 70);
    *((_DWORD *)this + 2) |= a3;
    *((_QWORD *)this + 9) = a6;
    if ( v25 )
    {
      FreeWrapper(v25);
      *((_QWORD *)this + 70) = 0;
    }
    if ( v9 )
    {
      *((_QWORD *)this + 70) = v9;
      v9 = 0;
    }
    goto LABEL_15;
  }
  InterpreterInfo = a2->InterpreterInfo;
  *((_DWORD *)this + 48) = InterpreterInfo[12];
  *((_QWORD *)this + 22) = *((_QWORD *)InterpreterInfo + 7);
  v17 = InterpreterInfo[12];
  v18 = (void *)*((_QWORD *)this + 23);
  *((_DWORD *)this + 49) = v17 - 1;
  if ( v18 )
    FreeWrapper(v18);
  v19 = AllocWrapper(saturated_mul(*((unsigned int *)this + 48), 0x14u));
  *((_QWORD *)this + 23) = v19;
  if ( v19 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 48); *(_DWORD *)(v23 + 4 * v22 + 16) = *(_DWORD *)(v21 + 8 * v24 + 16) )
    {
      v21 = *((_QWORD *)this + 22);
      v22 = 5 * i;
      v23 = *((_QWORD *)this + 23);
      v24 = 10 * i;
      i = (unsigned int)(i + 1);
      *(_OWORD *)(v23 + 4 * v22) = *(_OWORD *)(v21 + 8 * v24);
    }
    goto LABEL_11;
  }
  *((_DWORD *)this + 48) = 0;
  v15 = 14;
LABEL_21:
  if ( v9 )
    FreeWrapper(v9);
  return v15;
}

```

## disassembly

```asm
0x18000ff90  mov     r11, rsp
0x18000ff93  mov     [r11+8], rbx
0x18000ff97  mov     [r11+18h], rbp
0x18000ff9b  push    rsi
0x18000ff9c  push    rdi
0x18000ff9d  push    r12
0x18000ff9f  push    r14
0x18000ffa1  push    r15
0x18000ffa3  sub     rsp, 20h
0x18000ffa7  mov     r15d, [rdx]
0x18000ffaa  xor     esi, esi
0x18000ffac  mov     r12d, r9d
0x18000ffaf  mov     [r11+10h], rsi
0x18000ffb3  mov     ebp, r8d
0x18000ffb6  mov     r14, rdx
0x18000ffb9  mov     rbx, rcx
0x18000ffbc  lea     eax, [r15-40h]
0x18000ffc0  test    eax, 0FFFFFFDFh
0x18000ffc5  jnz     loc_180010199
0x18000ffcb  mov     rcx, [rsp+48h+CreatorDescriptor]; CreatorDescriptor
0x18000ffd3  test    rcx, rcx
0x18000ffd6  jz      short loc_18000FFF2
0x18000ffd8  lea     r8, [r11+10h]; void **
0x18000ffdc  xor     edx, edx; AutoInheritFlags
0x18000ffde  call    ?RpcpNormalizeSecurityDescriptor@@YAJPEAXKPEAPEAX@Z; RpcpNormalizeSecurityDescriptor(void *,ulong,void * *)
0x18000ffe3  mov     rsi, [rsp+48h+lpMem]
0x18000ffe8  mov     edi, eax
0x18000ffea  test    eax, eax
0x18000ffec  jnz     loc_18001014F
0x18000fff2  cmp     dword ptr [rbx+0C8h], 0
0x18000fff9  jnz     loc_1800101A0
0x18000ffff  test    dword ptr [r14+58h], 2000000h
0x180010007  jz      loc_180010172
0x18001000d  mov     rcx, [r14+50h]
0x180010011  mov     eax, [rcx+30h]
0x180010014  mov     [rbx+0C0h], eax
0x18001001a  mov     rax, [rcx+38h]
0x18001001e  mov     [rbx+0B0h], rax
0x180010025  mov     eax, [rcx+30h]
0x180010028  mov     rcx, [rbx+0B8h]; lpMem
0x18001002f  dec     eax
0x180010031  mov     [rbx+0C4h], eax
0x180010037  test    rcx, rcx
0x18001003a  jz      short loc_180010041
0x18001003c  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180010041  mov     ecx, [rbx+0C0h]
0x180010047  mov     eax, 14h
0x18001004c  mul     rcx
0x18001004f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180010056  cmovb   rax, rcx
0x18001005a  mov     rcx, rax; dwBytes
0x18001005d  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180010062  mov     [rbx+0B8h], rax
0x180010069  test    rax, rax
0x18001006c  jz      loc_180010188
0x180010072  xor     r10d, r10d
0x180010075  cmp     [rbx+0C0h], r10d
0x18001007c  jbe     short loc_1800100B7
0x18001007e  mov     rdx, [rbx+0B0h]
0x180010085  lea     r8, [r10+r10*4]
0x180010089  mov     rcx, [rbx+0B8h]
0x180010090  lea     r9, [r10+r10*4]
0x180010094  add     r9, r9
0x180010097  inc     r10d
0x18001009a  movups  xmm0, xmmword ptr [rdx+r9*8]
0x18001009f  movups  xmmword ptr [rcx+r8*4], xmm0
0x1800100a4  mov     eax, [rdx+r9*8+10h]
0x1800100a9  mov     [rcx+r8*4+10h], eax
0x1800100ae  cmp     r10d, [rbx+0C0h]
0x1800100b5  jb      short loc_18001007E
0x1800100b7  mov     r8, r15; Size
0x1800100ba  lea     rcx, [rbx+50h]; void *
0x1800100be  mov     rdx, r14; Src
0x1800100c1  call    memcpy_0
0x1800100c6  mov     dword ptr [rbx+8], 0
0x1800100cd  mov     eax, [rbx+8]
0x1800100d0  mov     rcx, [rbx+230h]; lpMem
0x1800100d7  or      eax, ebp
0x1800100d9  mov     [rbx+8], eax
0x1800100dc  mov     rax, [rsp+48h+arg_28]
0x1800100e1  mov     [rbx+48h], rax
0x1800100e5  test    rcx, rcx
0x1800100e8  jz      short loc_1800100FA
0x1800100ea  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800100ef  mov     qword ptr [rbx+230h], 0
0x1800100fa  test    rsi, rsi
0x1800100fd  jz      short loc_180010108
0x1800100ff  mov     [rbx+230h], rsi
0x180010106  xor     esi, esi
0x180010108  mov     eax, [rsp+48h+arg_20]
0x18001010c  mov     ecx, 7FFFFFFFh
0x180010111  cmp     eax, ecx
0x180010113  mov     [rbx+0CCh], r12d
0x18001011a  cmovnb  eax, ecx
0x18001011d  inc     dword ptr [rbx+16Ch]
0x180010123  mov     rcx, [rbx+238h]
0x18001012a  xor     edi, edi
0x18001012c  mov     [rbx+148h], eax
0x180010132  test    rcx, rcx
0x180010135  jnz     loc_18001021F
0x18001013b  mov     rcx, [rsp+48h+arg_38]; this
0x180010143  mov     [rbx+238h], rcx
0x18001014a  test    rcx, rcx
0x18001014d  jnz     short loc_180010181
0x18001014f  test    rsi, rsi
0x180010152  jnz     loc_180010230
0x180010158  mov     rbx, [rsp+48h+arg_0]
0x18001015d  mov     eax, edi
0x18001015f  mov     rbp, [rsp+48h+arg_10]
0x180010164  add     rsp, 20h
0x180010168  pop     r15
0x18001016a  pop     r14
0x18001016c  pop     r12
0x18001016e  pop     rdi
0x18001016f  pop     rsi
0x180010170  retn
0x180010172  mov     dword ptr [rbx+0C0h], 0
0x18001017c  jmp     loc_1800100B7
0x180010181  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x180010186  jmp     short loc_18001014F
0x180010188  mov     dword ptr [rbx+0C0h], 0
0x180010192  mov     edi, 0Eh
0x180010197  jmp     short loc_18001014F
0x180010199  mov     edi, 6B5h
0x18001019e  jmp     short loc_180010158
0x1800101a0  mov     eax, [rbx+8]
0x1800101a3  cmp     eax, ebp
0x1800101a5  jnz     short loc_1800101C4
0x1800101a7  mov     rax, [rsp+48h+arg_28]
0x1800101ac  cmp     [rbx+48h], rax
0x1800101b0  jnz     short loc_1800101C4
0x1800101b2  test    rsi, rsi
0x1800101b5  jnz     short loc_1800101C9
0x1800101b7  cmp     [rbx+230h], rsi
0x1800101be  jz      loc_180010108
0x1800101c4  test    rsi, rsi
0x1800101c7  jz      short loc_180010215
0x1800101c9  cmp     qword ptr [rbx+230h], 0
0x1800101d1  jz      short loc_180010215
0x1800101d3  mov     rcx, rsi; pSecurityDescriptor
0x1800101d6  call    cs:__imp_GetSecurityDescriptorLength
0x1800101dd  nop     dword ptr [rax+rax+00h]
0x1800101e2  mov     rcx, [rbx+230h]; pSecurityDescriptor
0x1800101e9  mov     edi, eax
0x1800101eb  call    cs:__imp_GetSecurityDescriptorLength
0x1800101f2  nop     dword ptr [rax+rax+00h]
0x1800101f7  cmp     edi, eax
0x1800101f9  jnz     short loc_180010215
0x1800101fb  mov     rdx, [rbx+230h]; Buf2
0x180010202  mov     r8d, edi; Size
0x180010205  mov     rcx, rsi; Buf1
0x180010208  call    memcmp_0
0x18001020d  test    eax, eax
0x18001020f  jz      loc_180010108
0x180010215  mov     edi, 57h ; 'W'
0x18001021a  jmp     loc_18001014F
0x18001021f  mov     rax, [rcx]
0x180010222  mov     rax, [rax+20h]
0x180010226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001022b  jmp     loc_18001013B
0x180010230  mov     rcx, rsi; lpMem
0x180010233  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180010238  jmp     loc_180010158
```
