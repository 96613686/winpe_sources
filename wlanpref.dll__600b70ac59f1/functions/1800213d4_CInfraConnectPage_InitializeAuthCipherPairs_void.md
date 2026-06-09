# CInfraConnectPage::InitializeAuthCipherPairs(void)

- ea: `0x1800213d4`
- end: `0x1800215ff`
- name: `?InitializeAuthCipherPairs@CInfraConnectPage@@AEAAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(CInfraConnectPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021a70`

## callees

- `0x180020800`
- `0x1800213d4`
- `0x180023054`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x18002158d`
- `wlanapi!WlanCloseHandle` at `0x18002158d`
- `wlanapi!WlanFreeMemory` at `0x1800215a6`
- `wlanapi!WlanFreeMemory` at `0x1800215a6`
- `wlanapi!WlanQueryInterface` at `0x18002148c`
- `wlanapi!WlanQueryInterface` at `0x18002148c`
- `wlanapi!WlanOpenHandle` at `0x18002144f`
- `wlanapi!WlanOpenHandle` at `0x18002144f`

## pseudocode

```c
__int64 __fastcall CInfraConnectPage::InitializeAuthCipherPairs(CInfraConnectPage *this)
{
  DWORD v2; // eax
  int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 i; // rdx
  __int64 v7; // rcx
  __int64 j; // rdx
  int v9; // r9d
  int v10; // r10d
  __int64 k; // rax
  __int64 v12; // r8
  void *phClientHandle; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+78h] [rbp+28h] BYREF
  DWORD pdwDataSize; // [rsp+80h] [rbp+30h] BYREF
  PVOID pMemory; // [rsp+88h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 22, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  }
  phClientHandle = 0;
  pdwDataSize = 0;
  pMemory = 0;
  pdwNegotiatedVersion = 0;
  v2 = WlanOpenHandle(1u, 0, &pdwNegotiatedVersion, &phClientHandle);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 145)
      && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      v5 = 24;
      goto LABEL_26;
    }
  }
  else
  {
    v2 = WlanQueryInterface(
           phClientHandle,
           (const GUID *)((char *)this + 360),
           wlan_intf_opcode_supported_infrastructure_auth_cipher_pairs,
           0,
           &pdwDataSize,
           &pMemory,
           0);
    v3 = v2;
    if ( !v2 )
    {
      if ( pMemory )
      {
        for ( i = 0; i != 14; ++i )
        {
          v7 = 3 * i;
          *(_BYTE *)(*((_QWORD *)this + 34) + 8 * v7 + 8) = 0;
        }
        for ( j = 0; (unsigned int)j < *(_DWORD *)pMemory; j = (unsigned int)(j + 1) )
        {
          v9 = *((_DWORD *)pMemory + 2 * j + 2);
          v10 = *((_DWORD *)pMemory + 2 * j + 1);
          for ( k = 0; k != 14; ++k )
          {
            v12 = *((_QWORD *)this + 34);
            if ( *(_DWORD *)(v12 + 24 * k) == v10 && *(_DWORD *)(v12 + 24 * k + 4) == v9 )
              *(_BYTE *)(v12 + 24 * k + 8) = 1;
          }
        }
      }
      goto LABEL_27;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 145)
      && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      v5 = 23;
LABEL_26:
      WPP_SF_d(v4[17], v5, WPP_1064fdabddc73196039d87943bb008b3_Traceguids, v2);
LABEL_27:
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    v4 = WPP_GLOBAL_Control;
  }
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 145) >= 4u && (*((_BYTE *)v4 + 148) & 1) != 0 )
    WPP_SF_(v4[17], 25, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800213d4  mov     [rsp-18h+arg_0], rbx
0x1800213d9  push    rbp
0x1800213da  push    rdi
0x1800213db  push    r15
0x1800213dd  mov     rbp, rsp
0x1800213e0  sub     rsp, 50h
0x1800213e4  mov     rdi, rcx
0x1800213e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213ee  lea     r15, WPP_GLOBAL_Control
0x1800213f5  cmp     rcx, r15
0x1800213f8  jz      short loc_180021424
0x1800213fa  cmp     byte ptr [rcx+91h], 4
0x180021401  jb      short loc_180021424
0x180021403  test    byte ptr [rcx+94h], 1
0x18002140a  jz      short loc_180021424
0x18002140c  mov     rcx, [rcx+88h]
0x180021413  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x18002141a  mov     edx, 16h
0x18002141f  call    WPP_SF_
0x180021424  xor     edx, edx; pReserved
0x180021426  mov     [rbp+phClientHandle], 0
0x18002142e  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180021432  mov     [rbp+arg_10], 0
0x180021439  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18002143d  mov     [rbp+pMemory], 0
0x180021445  mov     [rbp+pdwNegotiatedVersion], 0
0x18002144c  lea     ecx, [rdx+1]; dwClientVersion
0x18002144f  call    cs:__imp_WlanOpenHandle
0x180021455  mov     ebx, eax
0x180021457  test    eax, eax
0x180021459  jnz     loc_18002153F
0x18002145f  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180021463  lea     rax, [rbp+pMemory]
0x180021467  mov     [rsp+50h+pWlanOpcodeValueType], 0; pWlanOpcodeValueType
0x180021470  lea     rdx, [rdi+168h]; pInterfaceGuid
0x180021477  mov     [rsp+50h+ppData], rax; ppData
0x18002147c  lea     r8d, [rbx+9]; OpCode
0x180021480  lea     rax, [rbp+arg_10]
0x180021484  xor     r9d, r9d; pReserved
0x180021487  mov     [rsp+50h+pdwDataSize], rax; pdwDataSize
0x18002148c  call    cs:__imp_WlanQueryInterface
0x180021492  mov     ebx, eax
0x180021494  test    eax, eax
0x180021496  jz      short loc_1800214CC
0x180021498  mov     rcx, cs:WPP_GLOBAL_Control
0x18002149f  cmp     rcx, r15
0x1800214a2  jz      loc_18002157F
0x1800214a8  cmp     byte ptr [rcx+91h], 1
0x1800214af  jb      loc_18002157F
0x1800214b5  test    byte ptr [rcx+94h], 1
0x1800214bc  jz      loc_18002157F
0x1800214c2  mov     edx, 17h
0x1800214c7  jmp     loc_180021562
0x1800214cc  cmp     [rbp+pMemory], 0
0x1800214d1  jz      loc_180021578
0x1800214d7  xor     edx, edx
0x1800214d9  mov     rax, [rdi+110h]
0x1800214e0  lea     rcx, [rdx+rdx*2]
0x1800214e4  inc     rdx
0x1800214e7  mov     byte ptr [rax+rcx*8+8], 0
0x1800214ec  cmp     rdx, 0Eh
0x1800214f0  jnz     short loc_1800214D9
0x1800214f2  mov     rax, [rbp+pMemory]
0x1800214f6  xor     edx, edx
0x1800214f8  cmp     [rax], edx
0x1800214fa  jbe     short loc_180021578
0x1800214fc  mov     rax, [rbp+pMemory]
0x180021500  mov     r9d, [rax+rdx*8+8]
0x180021505  mov     r10d, [rax+rdx*8+4]
0x18002150a  xor     eax, eax
0x18002150c  mov     r8, [rdi+110h]
0x180021513  lea     rcx, [rax+rax*2]
0x180021517  cmp     [r8+rcx*8], r10d
0x18002151b  jnz     short loc_18002152A
0x18002151d  cmp     [r8+rcx*8+4], r9d
0x180021522  jnz     short loc_18002152A
0x180021524  mov     byte ptr [r8+rcx*8+8], 1
0x18002152a  inc     rax
0x18002152d  cmp     rax, 0Eh
0x180021531  jnz     short loc_18002150C
0x180021533  mov     rax, [rbp+pMemory]
0x180021537  inc     edx
0x180021539  cmp     edx, [rax]
0x18002153b  jb      short loc_1800214FC
0x18002153d  jmp     short loc_180021578
0x18002153f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021546  cmp     rcx, r15
0x180021549  jz      short loc_18002157F
0x18002154b  cmp     byte ptr [rcx+91h], 1
0x180021552  jb      short loc_18002157F
0x180021554  test    byte ptr [rcx+94h], 1
0x18002155b  jz      short loc_18002157F
0x18002155d  mov     edx, 18h
0x180021562  mov     rcx, [rcx+88h]
0x180021569  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x180021570  mov     r9d, eax
0x180021573  call    WPP_SF_d
0x180021578  mov     rcx, cs:WPP_GLOBAL_Control
0x18002157f  mov     rax, [rbp+phClientHandle]
0x180021583  test    rax, rax
0x180021586  jz      short loc_18002159A
0x180021588  xor     edx, edx; pReserved
0x18002158a  mov     rcx, rax; hClientHandle
0x18002158d  call    cs:__imp_WlanCloseHandle
0x180021593  mov     rcx, cs:WPP_GLOBAL_Control
0x18002159a  mov     rax, [rbp+pMemory]
0x18002159e  test    rax, rax
0x1800215a1  jz      short loc_1800215B3
0x1800215a3  mov     rcx, rax; pMemory
0x1800215a6  call    cs:__imp_WlanFreeMemory
0x1800215ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215b3  cmp     rcx, r15
0x1800215b6  jz      short loc_1800215E2
0x1800215b8  cmp     byte ptr [rcx+91h], 4
0x1800215bf  jb      short loc_1800215E2
0x1800215c1  test    byte ptr [rcx+94h], 1
0x1800215c8  jz      short loc_1800215E2
0x1800215ca  mov     rcx, [rcx+88h]
0x1800215d1  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x1800215d8  mov     edx, 19h
0x1800215dd  call    WPP_SF_
0x1800215e2  test    ebx, ebx
0x1800215e4  jle     short loc_1800215EF
0x1800215e6  movzx   ebx, bx
0x1800215e9  or      ebx, 80070000h
0x1800215ef  mov     eax, ebx
0x1800215f1  mov     rbx, [rsp+50h+arg_0]
0x1800215f6  add     rsp, 50h
0x1800215fa  pop     r15
0x1800215fc  pop     rdi
0x1800215fd  pop     rbp
0x1800215fe  retn
```
