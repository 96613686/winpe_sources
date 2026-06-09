# OneXControls::OnInitDialog(void)

- ea: `0x1800136f4`
- end: `0x1800137fa`
- name: `?OnInitDialog@OneXControls@@QEAAJXZ`
- size: `262`
- prototype: `__int64 __fastcall(OneXControls *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180013570`

## callees

- `0x1800136f4`
- `0x180014370`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x1800137d9`
- `wlanapi!WlanFreeMemory` at `0x1800137d9`
- `wlanapi!WlanOpenHandle` at `0x18001376a`
- `wlanapi!WlanOpenHandle` at `0x18001376a`
- `wlanapi!WlanCloseHandle` at `0x1800137ea`
- `wlanapi!WlanCloseHandle` at `0x1800137ea`
- `wlanapi!WlanQueryAutoConfigParameter` at `0x1800137a4`
- `wlanapi!WlanQueryAutoConfigParameter` at `0x1800137a4`

## pseudocode

```c
__int64 __fastcall OneXControls::OnInitDialog(OneXControls *this)
{
  __int64 v1; // rax
  __int64 v3; // rcx
  int v4; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  bool v7; // cc
  DWORD pdwDataSize; // [rsp+50h] [rbp+20h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+58h] [rbp+28h] BYREF
  PVOID pMemory; // [rsp+60h] [rbp+30h] BYREF
  void *phClientHandle; // [rsp+68h] [rbp+38h] BYREF

  v1 = *((_QWORD *)this + 5);
  pdwDataSize = 0;
  phClientHandle = 0;
  pMemory = 0;
  pdwNegotiatedVersion = 0;
  v3 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 72) + 552LL) + 32LL) + 424LL) + 48LL);
  *((_DWORD *)this + 13) = (*(_DWORD *)(v3 + 8) >> 2) & 1;
  if ( (*(_BYTE *)(v3 + 8) & 4) != 0 )
    v4 = *(_DWORD *)(v3 + 20);
  else
    v4 = 4;
  *((_DWORD *)this + 14) = v4;
  v5 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  v6 = v5;
  v7 = v5 <= 0;
  if ( v5
    || (v5 = WlanQueryAutoConfigParameter(
               phClientHandle,
               wlan_autoconf_opcode_allow_explicit_creds,
               0,
               &pdwDataSize,
               &pMemory,
               0),
        v6 = v5,
        v7 = v5 <= 0,
        v5) )
  {
    if ( !v7 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  else if ( pdwDataSize == 4 )
  {
    v6 = 0;
    *((_DWORD *)this + 29) = *(_DWORD *)pMemory;
    OneXControls::UpdateUIValues(this);
  }
  else
  {
    v6 = -2147024883;
  }
  if ( pMemory )
    WlanFreeMemory(pMemory);
  if ( phClientHandle )
    WlanCloseHandle(phClientHandle, 0);
  return v6;
}

```

## disassembly

```asm
0x1800136f4  push    rbp
0x1800136f6  push    rbx
0x1800136f7  push    rdi
0x1800136f8  mov     rbp, rsp
0x1800136fb  sub     rsp, 30h
0x1800136ff  mov     rax, [rcx+28h]
0x180013703  mov     rdi, rcx
0x180013706  mov     [rbp+pdwDataSize], 0
0x18001370d  mov     [rbp+phClientHandle], 0
0x180013715  mov     [rbp+pMemory], 0
0x18001371d  mov     [rbp+pdwNegotiatedVersion], 0
0x180013724  mov     rdx, [rax+48h]
0x180013728  mov     rax, [rdx+228h]
0x18001372f  mov     rdx, [rax+20h]
0x180013733  mov     rax, [rdx+1A8h]
0x18001373a  mov     rcx, [rax+30h]
0x18001373e  mov     eax, [rcx+8]
0x180013741  shr     eax, 2
0x180013744  and     eax, 1
0x180013747  mov     [rdi+34h], eax
0x18001374a  test    byte ptr [rcx+8], 4
0x18001374e  jz      short loc_180013755
0x180013750  mov     eax, [rcx+14h]
0x180013753  jmp     short loc_18001375A
0x180013755  mov     eax, 4
0x18001375a  xor     edx, edx; pReserved
0x18001375c  mov     [rdi+38h], eax
0x18001375f  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180013763  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180013767  lea     ecx, [rdx+2]; dwClientVersion
0x18001376a  call    cs:__imp_WlanOpenHandle
0x180013770  mov     ebx, eax
0x180013772  test    eax, eax
0x180013774  jz      short loc_180013783
0x180013776  jle     short loc_1800137D0
0x180013778  movzx   ebx, ax
0x18001377b  or      ebx, 80070000h
0x180013781  jmp     short loc_1800137D0
0x180013783  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180013787  lea     rax, [rbp+pMemory]
0x18001378b  xor     r8d, r8d; pReserved
0x18001378e  mov     [rsp+30h+pWlanOpcodeValueType], 0; pWlanOpcodeValueType
0x180013797  lea     r9, [rbp+pdwDataSize]; pdwDataSize
0x18001379b  mov     [rsp+30h+ppData], rax; ppData
0x1800137a0  lea     edx, [r8+4]; OpCode
0x1800137a4  call    cs:__imp_WlanQueryAutoConfigParameter
0x1800137aa  mov     ebx, eax
0x1800137ac  test    eax, eax
0x1800137ae  jnz     short loc_180013776
0x1800137b0  cmp     [rbp+pdwDataSize], 4
0x1800137b4  jz      short loc_1800137BD
0x1800137b6  mov     ebx, 8007000Dh
0x1800137bb  jmp     short loc_1800137D0
0x1800137bd  mov     rax, [rbp+pMemory]
0x1800137c1  xor     ebx, ebx
0x1800137c3  mov     ecx, [rax]
0x1800137c5  mov     [rdi+74h], ecx
0x1800137c8  mov     rcx, rdi; this
0x1800137cb  call    ?UpdateUIValues@OneXControls@@QEAAXXZ; OneXControls::UpdateUIValues(void)
0x1800137d0  mov     rcx, [rbp+pMemory]; pMemory
0x1800137d4  test    rcx, rcx
0x1800137d7  jz      short loc_1800137DF
0x1800137d9  call    cs:__imp_WlanFreeMemory
0x1800137df  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x1800137e3  test    rcx, rcx
0x1800137e6  jz      short loc_1800137F0
0x1800137e8  xor     edx, edx; pReserved
0x1800137ea  call    cs:__imp_WlanCloseHandle
0x1800137f0  mov     eax, ebx
0x1800137f2  add     rsp, 30h
0x1800137f6  pop     rdi
0x1800137f7  pop     rbx
0x1800137f8  pop     rbp
0x1800137f9  retn
```
