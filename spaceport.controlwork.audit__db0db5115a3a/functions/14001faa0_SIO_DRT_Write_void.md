# SIO_DRT::Write(void)

- ea: `0x14001faa0`
- end: `0x14001fbbe`
- name: `?Write@SIO_DRT@@AEAAJXZ`
- size: `286`
- prototype: `__int64 __fastcall(SIO_DRT *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003e380`
- `0x1400b0aa0`
- `0x1400b7200`

## callees

- `0x140008a00`
- `0x140009f80`
- `0x14000a070`
- `0x14001faa0`
- `0x140068000`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14001faf4`
- `ntoskrnl!RtlComputeCrc32` at `0x14001faf4`

## pseudocode

```c
__int64 __fastcall SIO_DRT::Write(SIO_DRT *this)
{
  __int64 v2; // rdi
  __int64 v3; // r8
  __int64 v4; // rsi
  ULONG v5; // ebx
  int v6; // ecx
  __int64 v7; // rax
  __int64 v8; // r8
  unsigned int v9; // ebx
  _BYTE v11[76]; // [rsp+20h] [rbp-128h] BYREF
  int v12; // [rsp+6Ch] [rbp-DCh]
  int v13; // [rsp+90h] [rbp-B8h]
  __int64 v14; // [rsp+98h] [rbp-B0h]
  __int64 v15; // [rsp+A8h] [rbp-A0h]
  int v16; // [rsp+B0h] [rbp-98h]
  __int16 v17; // [rsp+C8h] [rbp-80h]
  int v18; // [rsp+D4h] [rbp-74h]
  SIO_DRT *v19; // [rsp+108h] [rbp-40h]
  __int64 v20; // [rsp+110h] [rbp-38h]

  v2 = *(_QWORD *)(*((_QWORD *)this + 5) + 32LL) + *(unsigned int *)(*((_QWORD *)this + 5) + 44LL);
  SC_PACKET::SC_PACKET((SC_PACKET *)v11);
  v3 = 64;
  if ( *((_DWORD *)this + 13) )
    v3 = 72;
  v4 = *(_QWORD *)((char *)this + v3);
  v5 = 8 * *(_DWORD *)(v2 + 16) + 24;
  *(_DWORD *)(v2 + 20) = 0;
  *(_DWORD *)(v2 + 20) = RtlComputeCrc32(0, (PUCHAR)v2, v5);
  v6 = *(_DWORD *)(*((_QWORD *)this + 1) + 132LL);
  v7 = *((_QWORD *)this + 5);
  v12 |= 0x10000008u;
  v14 = v7;
  v13 = 1;
  v15 = v4;
  v17 = 7684;
  v19 = this;
  v16 = -v6 & (v5 + v6 - 1);
  v20 = *(_QWORD *)(*((_QWORD *)this + 2) + 392LL);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v20 + 8LL))(v20, v11);
  v9 = v18;
  if ( v18 >= 0 )
  {
    LOBYTE(v8) = 3;
    v20 = *((_QWORD *)this + 2);
    SC_DISPATCH::Dispatch(v20, v11, v8);
    v9 = v18;
  }
  SIO_LOG_PACKET::~SIO_LOG_PACKET((SIO_LOG_PACKET *)v11);
  return v9;
}

```

## disassembly

```asm
0x14001faa0  push    rbx
0x14001faa2  push    rbp
0x14001faa3  push    rsi
0x14001faa4  push    rdi
0x14001faa5  sub     rsp, 128h
0x14001faac  mov     rax, [rcx+28h]
0x14001fab0  mov     rbp, rcx
0x14001fab3  lea     rcx, [rsp+148h+var_128]; this
0x14001fab8  mov     edi, [rax+2Ch]
0x14001fabb  add     rdi, [rax+20h]
0x14001fabf  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14001fac4  cmp     dword ptr [rbp+34h], 0
0x14001fac8  mov     eax, 48h ; 'H'
0x14001facd  mov     r8d, 40h ; '@'
0x14001fad3  mov     rdx, rdi; Buffer
0x14001fad6  cmovnz  r8d, eax
0x14001fada  mov     eax, [rdi+10h]
0x14001fadd  xor     ecx, ecx; InitialCrc
0x14001fadf  mov     rsi, [r8+rbp]
0x14001fae3  lea     ebx, ds:18h[rax*8]
0x14001faea  mov     r8d, ebx; Length
0x14001faed  mov     dword ptr [rdi+14h], 0
0x14001faf4  call    cs:__imp_RtlComputeCrc32
0x14001fafb  nop     dword ptr [rax+rax+00h]
0x14001fb00  mov     [rdi+14h], eax
0x14001fb03  lea     rdx, [rsp+148h+var_128]
0x14001fb08  mov     rax, [rbp+8]
0x14001fb0c  mov     ecx, [rax+84h]
0x14001fb12  mov     rax, [rbp+28h]
0x14001fb16  or      [rsp+148h+var_DC], 10000008h
0x14001fb1e  mov     [rsp+148h+var_B0], rax
0x14001fb26  lea     eax, [rcx-1]
0x14001fb29  mov     [rsp+148h+var_B8], 1
0x14001fb34  add     eax, ebx
0x14001fb36  mov     [rsp+148h+var_A0], rsi
0x14001fb3e  neg     ecx
0x14001fb40  mov     [rsp+148h+var_80], 1E04h
0x14001fb4a  and     eax, ecx
0x14001fb4c  mov     [rsp+148h+var_40], rbp
0x14001fb54  mov     [rsp+148h+var_98], eax
0x14001fb5b  mov     rax, [rbp+10h]
0x14001fb5f  mov     rcx, [rax+188h]
0x14001fb66  mov     [rsp+148h+var_38], rcx
0x14001fb6e  mov     rax, [rcx]
0x14001fb71  mov     rax, [rax+8]
0x14001fb75  call    _guard_dispatch_icall
0x14001fb7a  mov     ebx, [rsp+148h+var_74]
0x14001fb81  test    ebx, ebx
0x14001fb83  js      short loc_14001FBA5
0x14001fb85  mov     rcx, [rbp+10h]
0x14001fb89  lea     rdx, [rsp+148h+var_128]
0x14001fb8e  mov     r8b, 3
0x14001fb91  mov     [rsp+148h+var_38], rcx
0x14001fb99  call    ?Dispatch@SC_DISPATCH@@QEAAXPEAVSC_PACKET@@W4_SC_OPERATION@@@Z; SC_DISPATCH::Dispatch(SC_PACKET *,_SC_OPERATION)
0x14001fb9e  mov     ebx, [rsp+148h+var_74]
0x14001fba5  lea     rcx, [rsp+148h+var_128]; this
0x14001fbaa  call    ??1SIO_LOG_PACKET@@UEAA@XZ; SIO_LOG_PACKET::~SIO_LOG_PACKET(void)
0x14001fbaf  mov     eax, ebx
0x14001fbb1  add     rsp, 128h
0x14001fbb8  pop     rdi
0x14001fbb9  pop     rsi
0x14001fbba  pop     rbp
0x14001fbbb  pop     rbx
0x14001fbbc  retn
```
