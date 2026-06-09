# SecMgrGetPortState(MSMSEC_PORT_CONTEXT *,MSMSEC_PEER_STATE * *)

- ea: `0x18000b3d4`
- end: `0x18000b6d5`
- name: `?SecMgrGetPortState@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAPEAUMSMSEC_PEER_STATE@@@Z`
- size: `769`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *, struct MSMSEC_PEER_STATE **)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18000bc44`
- `0x180053c30`
- `0x180058e30`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a5c0`
- `0x18000b3d4`
- `0x18000bbcc`
- `0x18000c730`
- `0x18000e620`
- `0x180044554`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18000b49b`
- `MobileNetworking!ReleaseWriteLock` at `0x18000b49b`
- `MobileNetworking!AcquireWriteLock` at `0x18000b44c`
- `MobileNetworking!AcquireWriteLock` at `0x18000b44c`

## pseudocode

```c
__int64 __fastcall SecMgrGetPortState(struct MSMSEC_PORT_CONTEXT *a1, struct MSMSEC_PEER_STATE **a2, int a3)
{
  PVOID *v5; // rcx
  int v6; // r8d
  __int64 v7; // r9
  int *v8; // rcx
  int v9; // r15d
  int v10; // r12d
  unsigned int OneXState; // eax
  unsigned int v12; // edi
  _QWORD *v13; // rcx
  unsigned int v15; // ebp
  SIZE_T v16; // rcx
  _DWORD *v17; // rbx
  int v18; // eax
  const void *v19; // rdx
  __int64 v20; // rdx
  __int128 Size; // [rsp+30h] [rbp-38h] BYREF
  _DWORD *v22; // [rsp+70h] [rbp+8h] BYREF

  v22 = 0;
  Size = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 169, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v5[7], 11, a3, *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), (__int64)">>> Locking >>>");
  }
  AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrGetPortState", 2115);
  v7 = *((_QWORD *)a1 + 3);
  v8 = *(int **)(*(_QWORD *)(v7 + 2784) + 24LL);
  v9 = *v8;
  v10 = v8[1];
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v6, *(_DWORD *)(v7 + 2496), (__int64)"<<< Unlocking <<<");
  ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrGetPortState", 2122);
  OneXState = AuthMgrGetOneXState((struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 920), (struct MSMSEC_RAW_DATA *)&Size);
  v12 = OneXState;
  if ( OneXState )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_12;
    v20 = 170;
LABEL_30:
    WPP_SF_d(v13[7], v20, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, OneXState);
LABEL_12:
    FreeMSMSecMemory(&v22);
    goto LABEL_13;
  }
  v15 = Size;
  v16 = (unsigned int)(Size + 56);
  if ( (unsigned int)v16 < (unsigned int)Size )
  {
    v12 = 534;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 171, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
    goto LABEL_12;
  }
  OneXState = AllocateMSMSecMemory(v16);
  v12 = OneXState;
  if ( OneXState )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_12;
    v20 = 172;
    goto LABEL_30;
  }
  v17 = v22;
  *v22 = *(_DWORD *)((char *)a1 + 302);
  *((_WORD *)v17 + 2) = *((_WORD *)a1 + 153);
  *(_DWORD *)((char *)v17 + 6) = *((_DWORD *)a1 + 74);
  *((_WORD *)v17 + 5) = *((_WORD *)a1 + 150);
  v17[3] = v9;
  v17[4] = v10;
  v18 = MapPortSecState(*((unsigned int *)a1 + 110));
  v19 = (const void *)*((_QWORD *)&Size + 1);
  v17[5] = v18;
  v17[6] = *((_DWORD *)a1 + 297);
  v17[7] = *((_DWORD *)a1 + 298);
  v17[10] = v15;
  v17[8] = *((_DWORD *)a1 + 120);
  v17[9] = *((_DWORD *)a1 + 121);
  memcpy_0(v17 + 14, v19, v15);
  *a2 = (struct MSMSEC_PEER_STATE *)v17;
LABEL_13:
  if ( *((_QWORD *)&Size + 1) )
    FreeMSMSecMemory((char *)&Size + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 173, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18000b3d4  mov     rax, rsp
0x18000b3d7  mov     [rax+10h], rbx
0x18000b3db  mov     [rax+18h], rbp
0x18000b3df  push    rsi
0x18000b3e0  push    rdi
0x18000b3e1  push    r12
0x18000b3e3  push    r13
0x18000b3e5  push    r15
0x18000b3e7  sub     rsp, 40h
0x18000b3eb  xorps   xmm0, xmm0
0x18000b3ee  mov     qword ptr [rax+8], 0
0x18000b3f6  movups  xmmword ptr [rax-38h], xmm0
0x18000b3fa  mov     r13, rdx
0x18000b3fd  mov     rsi, rcx
0x18000b400  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b407  lea     rbx, WPP_GLOBAL_Control
0x18000b40e  mov     ebp, 0Bh
0x18000b413  mov     edi, 100h
0x18000b418  cmp     rcx, rbx
0x18000b41b  jz      short loc_18000B434
0x18000b41d  test    [rcx+44h], edi
0x18000b420  jnz     loc_18000B5CC
0x18000b426  cmp     rcx, rbx
0x18000b429  jz      short loc_18000B434
0x18000b42b  test    [rcx+44h], edi
0x18000b42e  jnz     loc_18000B5ED
0x18000b434  mov     rcx, [rsi+18h]
0x18000b438  lea     r8, aSecmgrgetports; "SecMgrGetPortState"
0x18000b43f  mov     r9d, 843h
0x18000b445  lea     rdx, [rcx+9D0h]
0x18000b44c  call    cs:__imp_AcquireWriteLock
0x18000b453  nop     dword ptr [rax+rax+00h]
0x18000b458  mov     r9, [rsi+18h]
0x18000b45c  mov     rax, [r9+0AE0h]
0x18000b463  mov     rcx, [rax+18h]
0x18000b467  mov     r15d, [rcx]
0x18000b46a  mov     r12d, [rcx+4]
0x18000b46e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b475  cmp     rcx, rbx
0x18000b478  jz      short loc_18000B483
0x18000b47a  test    [rcx+44h], edi
0x18000b47d  jnz     loc_18000B614
0x18000b483  mov     rcx, [rsi+18h]
0x18000b487  lea     r8, aSecmgrgetports; "SecMgrGetPortState"
0x18000b48e  mov     r9d, 84Ah
0x18000b494  lea     rdx, [rcx+9D0h]
0x18000b49b  call    cs:__imp_ReleaseWriteLock
0x18000b4a2  nop     dword ptr [rax+rax+00h]
0x18000b4a7  lea     rcx, [rsi+398h]; struct MSMSEC_PORT_AUTH_CONTEXT *
0x18000b4ae  lea     rdx, [rsp+68h+Size]; struct MSMSEC_RAW_DATA *
0x18000b4b3  call    ?AuthMgrGetOneXState@@YAKPEAUMSMSEC_PORT_AUTH_CONTEXT@@PEAUMSMSEC_RAW_DATA@@@Z; AuthMgrGetOneXState(MSMSEC_PORT_AUTH_CONTEXT *,MSMSEC_RAW_DATA *)
0x18000b4b8  mov     edi, eax
0x18000b4ba  test    eax, eax
0x18000b4bc  jz      short loc_18000B51F
0x18000b4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4c5  cmp     rcx, rbx
0x18000b4c8  jnz     loc_18000B637
0x18000b4ce  lea     rcx, [rsp+68h+arg_0]
0x18000b4d3  call    FreeMSMSecMemory
0x18000b4d8  cmp     [rsp+68h+Src], 0
0x18000b4de  jz      short loc_18000B4EA
0x18000b4e0  lea     rcx, [rsp+68h+Src]
0x18000b4e5  call    FreeMSMSecMemory
0x18000b4ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4f1  cmp     rcx, rbx
0x18000b4f4  jz      short loc_18000B503
0x18000b4f6  test    dword ptr [rcx+44h], 100h
0x18000b4fd  jnz     loc_18000B6B8
0x18000b503  lea     r11, [rsp+68h+var_28]
0x18000b508  mov     eax, edi
0x18000b50a  mov     rbx, [r11+38h]
0x18000b50e  mov     rbp, [r11+40h]
0x18000b512  mov     rsp, r11
0x18000b515  pop     r15
0x18000b517  pop     r13
0x18000b519  pop     r12
0x18000b51b  pop     rdi
0x18000b51c  pop     rsi
0x18000b51d  retn
0x18000b51f  mov     ebp, dword ptr [rsp+68h+Size]
0x18000b523  lea     ecx, [rbp+38h]; dwBytes
0x18000b526  cmp     ecx, ebp
0x18000b528  jb      loc_18000B648
0x18000b52e  lea     rdx, [rsp+68h+arg_0]
0x18000b533  call    AllocateMSMSecMemory
0x18000b538  mov     edi, eax
0x18000b53a  test    eax, eax
0x18000b53c  jnz     loc_18000B681
0x18000b542  mov     eax, [rsi+12Eh]
0x18000b548  mov     rbx, [rsp+68h+arg_0]
0x18000b54d  mov     [rbx], eax
0x18000b54f  movzx   eax, word ptr [rsi+132h]
0x18000b556  mov     [rbx+4], ax
0x18000b55a  mov     eax, [rsi+128h]
0x18000b560  mov     [rbx+6], eax
0x18000b563  movzx   eax, word ptr [rsi+12Ch]
0x18000b56a  mov     [rbx+0Ah], ax
0x18000b56e  mov     [rbx+0Ch], r15d
0x18000b572  mov     [rbx+10h], r12d
0x18000b576  mov     ecx, [rsi+1B8h]
0x18000b57c  call    ?MapPortSecState@@YA?AW4MSMSEC_STATE@@W4MSMSEC_PORT_SEC_STATE@@@Z; MapPortSecState(MSMSEC_PORT_SEC_STATE)
0x18000b581  mov     rdx, [rsp+68h+Src]; Src
0x18000b586  lea     rcx, [rbx+38h]; void *
0x18000b58a  mov     [rbx+14h], eax
0x18000b58d  mov     r8d, ebp; Size
0x18000b590  mov     eax, [rsi+4A4h]
0x18000b596  mov     [rbx+18h], eax
0x18000b599  mov     eax, [rsi+4A8h]
0x18000b59f  mov     [rbx+1Ch], eax
0x18000b5a2  mov     [rbx+28h], ebp
0x18000b5a5  mov     eax, [rsi+1E0h]
0x18000b5ab  mov     [rbx+20h], eax
0x18000b5ae  mov     eax, [rsi+1E4h]
0x18000b5b4  mov     [rbx+24h], eax
0x18000b5b7  call    memcpy_0
0x18000b5bc  mov     [r13+0], rbx
0x18000b5c0  lea     rbx, WPP_GLOBAL_Control
0x18000b5c7  jmp     loc_18000B4D8
0x18000b5cc  mov     rcx, [rcx+38h]
0x18000b5d0  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18000b5d7  mov     edx, 0A9h
0x18000b5dc  call    WPP_SF_
0x18000b5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5e8  jmp     loc_18000B426
0x18000b5ed  mov     r9, [rsi+18h]
0x18000b5f1  lea     rax, aLocking; ">>> Locking >>>"
0x18000b5f8  mov     rcx, [rcx+38h]
0x18000b5fc  mov     edx, ebp
0x18000b5fe  mov     [rsp+68h+var_48], rax
0x18000b603  mov     r9d, [r9+9C0h]
0x18000b60a  call    WPP_SF_Ls
0x18000b60f  jmp     loc_18000B434
0x18000b614  mov     r9d, [r9+9C0h]
0x18000b61b  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x18000b622  mov     rcx, [rcx+38h]
0x18000b626  mov     edx, ebp
0x18000b628  mov     [rsp+68h+var_48], rax
0x18000b62d  call    WPP_SF_Ls
0x18000b632  jmp     loc_18000B483
0x18000b637  test    byte ptr [rcx+44h], 1
0x18000b63b  jz      loc_18000B4CE
0x18000b641  mov     edx, 0AAh
0x18000b646  jmp     short loc_18000B6A0
0x18000b648  mov     edi, 216h
0x18000b64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b654  cmp     rcx, rbx
0x18000b657  jz      loc_18000B4CE
0x18000b65d  test    byte ptr [rcx+44h], 1
0x18000b661  jz      loc_18000B4CE
0x18000b667  mov     rcx, [rcx+38h]
0x18000b66b  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18000b672  mov     edx, 0ABh
0x18000b677  call    WPP_SF_
0x18000b67c  jmp     loc_18000B4CE
0x18000b681  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b688  cmp     rcx, rbx
0x18000b68b  jz      loc_18000B4CE
0x18000b691  test    byte ptr [rcx+44h], 1
0x18000b695  jz      loc_18000B4CE
0x18000b69b  mov     edx, 0ACh
0x18000b6a0  mov     rcx, [rcx+38h]
0x18000b6a4  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18000b6ab  mov     r9d, eax
0x18000b6ae  call    WPP_SF_d
0x18000b6b3  jmp     loc_18000B4CE
0x18000b6b8  mov     rcx, [rcx+38h]
0x18000b6bc  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18000b6c3  mov     edx, 0ADh
0x18000b6c8  mov     r9d, edi
0x18000b6cb  call    WPP_SF_d
0x18000b6d0  jmp     loc_18000B503
```
