# CUPnPValidAddressInfo::CreateAndInsertNewAddress(_SOCKET_ADDRESS *,_IP_ADAPTER_ADDRESSES_LH *,_LIST_ENTRY *)

- ea: `0x18000f7e8`
- end: `0x18000f941`
- name: `?CreateAndInsertNewAddress@CUPnPValidAddressInfo@@AEAAJPEAU_SOCKET_ADDRESS@@PEAU_IP_ADAPTER_ADDRESSES_LH@@PEAU_LIST_ENTRY@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(CUPnPValidAddressInfo *__hidden this, struct _SOCKET_ADDRESS *, struct _IP_ADAPTER_ADDRESSES_LH *, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000df04`
- `0x180010a40`

## callees

- `0x18000e55c`
- `0x18000f7e8`
- `0x1800271fc`
- `0x1800287d0`
- `0x180037dd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f855`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f855`

## pseudocode

```c
__int64 __fastcall CUPnPValidAddressInfo::CreateAndInsertNewAddress(
        CUPnPValidAddressInfo *this,
        struct _SOCKET_ADDRESS *a2,
        struct _IP_ADAPTER_ADDRESSES_LH *a3,
        struct _LIST_ENTRY *a4)
{
  char *AdapterName; // rcx
  unsigned int v8; // ebx
  LPCSTR v9; // rcx
  __int64 v10; // rdx
  struct _GUID *v11; // rax
  struct _GUID *v12; // rdi
  struct _LIST_ENTRY *Flink; // rax
  struct _GUID v15; // [rsp+20h] [rbp-48h] BYREF

  AdapterName = a3->AdapterName;
  v15 = 0;
  v8 = ConvertAdapterNameStringToGuid(AdapterName, &v15);
  if ( (v8 & 0x80000000) == 0 )
  {
    v11 = (struct _GUID *)malloc(0xE8u);
    v12 = v11;
    if ( v11 )
    {
      v11[13].Data1 = a3->IfIndex;
      *(_DWORD *)&v11[13].Data2 = a3->Ipv6IfIndex;
      v11[8] = v15;
      memcpy_0(v11, a2->lpSockaddr, a2->iSockaddrLength);
      v12[9] = *(struct _GUID *)a3->ZoneIndices;
      v12[10] = *(struct _GUID *)&a3->ZoneIndices[4];
      v12[11] = *(struct _GUID *)&a3->ZoneIndices[8];
      v12[12] = *(struct _GUID *)&a3->ZoneIndices[12];
      Flink = a4->Flink;
      *(_QWORD *)v12[13].Data4 = a4->Flink;
      *(_QWORD *)&v12[14].Data1 = a4;
      Flink->Blink = (struct _LIST_ENTRY *)v12[13].Data4;
      a4->Flink = (struct _LIST_ENTRY *)v12[13].Data4;
      return v8;
    }
    v8 = -2147024882;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      v10 = 42;
      goto LABEL_9;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      v10 = 41;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, v8);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000f7e8  push    rbx
0x18000f7ea  push    rsi
0x18000f7eb  push    rdi
0x18000f7ec  push    r14
0x18000f7ee  push    r15
0x18000f7f0  sub     rsp, 40h
0x18000f7f4  mov     rax, cs:__security_cookie
0x18000f7fb  xor     rax, rsp
0x18000f7fe  mov     [rsp+68h+var_38], rax
0x18000f803  mov     rcx, [r8+10h]; char *
0x18000f807  mov     r15, rdx
0x18000f80a  xorps   xmm0, xmm0
0x18000f80d  lea     rdx, [rsp+68h+var_48]; struct _GUID *
0x18000f812  movups  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x18000f817  mov     r14, r9
0x18000f81a  mov     rsi, r8
0x18000f81d  call    ?ConvertAdapterNameStringToGuid@@YAJPEADPEAU_GUID@@@Z; ConvertAdapterNameStringToGuid(char *,_GUID *)
0x18000f822  mov     ebx, eax
0x18000f824  test    eax, eax
0x18000f826  jns     short loc_18000F850
0x18000f828  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f82f  lea     rax, WPP_GLOBAL_Control
0x18000f836  cmp     rcx, rax
0x18000f839  jz      loc_18000F925
0x18000f83f  test    byte ptr [rcx+1Ch], 1
0x18000f843  jz      loc_18000F925
0x18000f849  mov     edx, 29h ; ')'
0x18000f84e  jmp     short loc_18000F892
0x18000f850  mov     ecx, 0E8h; Size
0x18000f855  call    cs:__imp_malloc
0x18000f85c  nop     dword ptr [rax+rax+00h]
0x18000f861  mov     rdi, rax
0x18000f864  test    rax, rax
0x18000f867  jnz     short loc_18000F8A7
0x18000f869  mov     ebx, 8007000Eh
0x18000f86e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f875  lea     rax, WPP_GLOBAL_Control
0x18000f87c  cmp     rcx, rax
0x18000f87f  jz      loc_18000F925
0x18000f885  test    byte ptr [rcx+1Ch], 1
0x18000f889  jz      loc_18000F925
0x18000f88f  lea     edx, [rdi+2Ah]
0x18000f892  mov     rcx, [rcx+10h]
0x18000f896  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000f89d  mov     r9d, ebx
0x18000f8a0  call    WPP_SF_d
0x18000f8a5  jmp     short loc_18000F925
0x18000f8a7  mov     eax, [rsi+4]
0x18000f8aa  mov     rcx, rdi; void *
0x18000f8ad  mov     [rdi+0D0h], eax
0x18000f8b3  mov     eax, [rsi+6Ch]
0x18000f8b6  mov     [rdi+0D4h], eax
0x18000f8bc  movups  xmm0, xmmword ptr [rsp+68h+var_48.Data1]
0x18000f8c1  movdqu  xmmword ptr [rdi+80h], xmm0
0x18000f8c9  movsxd  r8, dword ptr [r15+8]; Size
0x18000f8cd  mov     rdx, [r15]; Src
0x18000f8d0  call    memcpy_0
0x18000f8d5  movups  xmm0, xmmword ptr [rsi+70h]
0x18000f8d9  lea     rcx, [rdi+0D8h]
0x18000f8e0  movups  xmmword ptr [rdi+90h], xmm0
0x18000f8e7  movups  xmm1, xmmword ptr [rsi+80h]
0x18000f8ee  movups  xmmword ptr [rdi+0A0h], xmm1
0x18000f8f5  movups  xmm0, xmmword ptr [rsi+90h]
0x18000f8fc  movups  xmmword ptr [rdi+0B0h], xmm0
0x18000f903  movups  xmm1, xmmword ptr [rsi+0A0h]
0x18000f90a  movups  xmmword ptr [rdi+0C0h], xmm1
0x18000f911  mov     rax, [r14]
0x18000f914  mov     [rcx], rax
0x18000f917  mov     [rdi+0E0h], r14
0x18000f91e  mov     [rax+8], rcx
0x18000f922  mov     [r14], rcx
0x18000f925  mov     eax, ebx
0x18000f927  mov     rcx, [rsp+68h+var_38]
0x18000f92c  xor     rcx, rsp; StackCookie
0x18000f92f  call    __security_check_cookie
0x18000f934  add     rsp, 40h
0x18000f938  pop     r15
0x18000f93a  pop     r14
0x18000f93c  pop     rdi
0x18000f93d  pop     rsi
0x18000f93e  pop     rbx
0x18000f93f  retn
```
