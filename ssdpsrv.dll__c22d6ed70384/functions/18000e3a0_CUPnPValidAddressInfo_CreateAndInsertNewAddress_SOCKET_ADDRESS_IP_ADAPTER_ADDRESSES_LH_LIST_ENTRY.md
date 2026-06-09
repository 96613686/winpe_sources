# CUPnPValidAddressInfo::CreateAndInsertNewAddress(_SOCKET_ADDRESS *,_IP_ADAPTER_ADDRESSES_LH *,_LIST_ENTRY *)

- ea: `0x18000e3a0`
- end: `0x18000e4f2`
- name: `?CreateAndInsertNewAddress@CUPnPValidAddressInfo@@AEAAJPEAU_SOCKET_ADDRESS@@PEAU_IP_ADAPTER_ADDRESSES_LH@@PEAU_LIST_ENTRY@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(CUPnPValidAddressInfo *__hidden this, struct _SOCKET_ADDRESS *, struct _IP_ADAPTER_ADDRESSES_LH *, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cc04`
- `0x18000f660`

## callees

- `0x18000d22c`
- `0x18000e3a0`
- `0x1800255a8`
- `0x180026a30`
- `0x180035298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e40d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e40d`

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
0x18000e3a0  push    rbx
0x18000e3a2  push    rsi
0x18000e3a3  push    rdi
0x18000e3a4  push    r14
0x18000e3a6  push    r15
0x18000e3a8  sub     rsp, 40h
0x18000e3ac  mov     rax, cs:__security_cookie
0x18000e3b3  xor     rax, rsp
0x18000e3b6  mov     [rsp+68h+var_38], rax
0x18000e3bb  mov     rcx, [r8+10h]; char *
0x18000e3bf  mov     r15, rdx
0x18000e3c2  xorps   xmm0, xmm0
0x18000e3c5  lea     rdx, [rsp+68h+var_48]; struct _GUID *
0x18000e3ca  movups  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x18000e3cf  mov     r14, r9
0x18000e3d2  mov     rsi, r8
0x18000e3d5  call    ?ConvertAdapterNameStringToGuid@@YAJPEADPEAU_GUID@@@Z; ConvertAdapterNameStringToGuid(char *,_GUID *)
0x18000e3da  mov     ebx, eax
0x18000e3dc  test    eax, eax
0x18000e3de  jns     short loc_18000E408
0x18000e3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3e7  lea     rax, WPP_GLOBAL_Control
0x18000e3ee  cmp     rcx, rax
0x18000e3f1  jz      loc_18000E4D7
0x18000e3f7  test    byte ptr [rcx+1Ch], 1
0x18000e3fb  jz      loc_18000E4D7
0x18000e401  mov     edx, 29h ; ')'
0x18000e406  jmp     short loc_18000E444
0x18000e408  mov     ecx, 0E8h; Size
0x18000e40d  call    cs:__imp_malloc
0x18000e413  mov     rdi, rax
0x18000e416  test    rax, rax
0x18000e419  jnz     short loc_18000E459
0x18000e41b  mov     ebx, 8007000Eh
0x18000e420  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e427  lea     rax, WPP_GLOBAL_Control
0x18000e42e  cmp     rcx, rax
0x18000e431  jz      loc_18000E4D7
0x18000e437  test    byte ptr [rcx+1Ch], 1
0x18000e43b  jz      loc_18000E4D7
0x18000e441  lea     edx, [rdi+2Ah]
0x18000e444  mov     rcx, [rcx+10h]
0x18000e448  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000e44f  mov     r9d, ebx
0x18000e452  call    WPP_SF_d
0x18000e457  jmp     short loc_18000E4D7
0x18000e459  mov     eax, [rsi+4]
0x18000e45c  mov     rcx, rdi; void *
0x18000e45f  mov     [rdi+0D0h], eax
0x18000e465  mov     eax, [rsi+6Ch]
0x18000e468  mov     [rdi+0D4h], eax
0x18000e46e  movups  xmm0, xmmword ptr [rsp+68h+var_48.Data1]
0x18000e473  movdqu  xmmword ptr [rdi+80h], xmm0
0x18000e47b  movsxd  r8, dword ptr [r15+8]; Size
0x18000e47f  mov     rdx, [r15]; Src
0x18000e482  call    memcpy_0
0x18000e487  movups  xmm0, xmmword ptr [rsi+70h]
0x18000e48b  lea     rcx, [rdi+0D8h]
0x18000e492  movups  xmmword ptr [rdi+90h], xmm0
0x18000e499  movups  xmm1, xmmword ptr [rsi+80h]
0x18000e4a0  movups  xmmword ptr [rdi+0A0h], xmm1
0x18000e4a7  movups  xmm0, xmmword ptr [rsi+90h]
0x18000e4ae  movups  xmmword ptr [rdi+0B0h], xmm0
0x18000e4b5  movups  xmm1, xmmword ptr [rsi+0A0h]
0x18000e4bc  movups  xmmword ptr [rdi+0C0h], xmm1
0x18000e4c3  mov     rax, [r14]
0x18000e4c6  mov     [rcx], rax
0x18000e4c9  mov     [rdi+0E0h], r14
0x18000e4d0  mov     [rax+8], rcx
0x18000e4d4  mov     [r14], rcx
0x18000e4d7  mov     eax, ebx
0x18000e4d9  mov     rcx, [rsp+68h+var_38]
0x18000e4de  xor     rcx, rsp; StackCookie
0x18000e4e1  call    __security_check_cookie
0x18000e4e6  add     rsp, 40h
0x18000e4ea  pop     r15
0x18000e4ec  pop     r14
0x18000e4ee  pop     rdi
0x18000e4ef  pop     rsi
0x18000e4f0  pop     rbx
0x18000e4f1  retn
```
