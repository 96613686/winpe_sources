# CWcnSoftApApiWrapper::EnableSoftAp(void)

- ea: `0x180052520`
- end: `0x180052734`
- name: `?EnableSoftAp@CWcnSoftApApiWrapper@@QEAAJXZ`
- size: `532`
- prototype: `__int64 __fastcall(CWcnSoftApApiWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800495a0`

## callees

- `0x180004f2c`
- `0x180004fb8`
- `0x180005014`
- `0x180052290`
- `0x180052520`
- `0x1800529d4`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052577`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052577`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800526de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800526de`
- `wlanapi!WFDRegisterVMgrCallerInt` at `0x180052653`
- `wlanapi!WFDRegisterVMgrCallerInt` at `0x180052653`
- `wlanapi!WFDOpenHandleInt` at `0x180052608`
- `wlanapi!WFDOpenHandleInt` at `0x180052608`
- `wlanapi!WlanStartAP` at `0x180052682`
- `wlanapi!WlanStartAP` at `0x180052682`
- `wlanapi!WlanOpenHandle` at `0x1800525a0`
- `wlanapi!WlanOpenHandle` at `0x1800525a0`

## pseudocode

```c
__int64 __fastcall CWcnSoftApApiWrapper::EnableSoftAp(CWcnSoftApApiWrapper *this)
{
  signed int v1; // ebx
  const char *Indent; // rax
  __int64 v4; // r10
  int v5; // ecx
  signed int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  int started; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // r10
  DWORD pdwNegotiatedVersion; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  pdwNegotiatedVersion = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 10, WPP_8ca0ecc9a63d3d47c093cf22e6bad64a_Traceguids, Indent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v5 = *((_DWORD *)this + 14);
  if ( v5 )
  {
    if ( v5 != 1 )
      goto LABEL_32;
    goto LABEL_23;
  }
  v6 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, (PHANDLE)this + 8);
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    else
      v7 = v6;
    v1 = v7 | 0x80000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_30;
    v9 = 11;
    goto LABEL_14;
  }
  v6 = WFDOpenHandleInt(1, &pdwNegotiatedVersion, (char *)this + 72);
  if ( v6 )
  {
    if ( v6 > 0 )
      v10 = (unsigned __int16)v6 | 0x80070000;
    else
      v10 = v6;
    v1 = v10 | 0x80000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_30;
    v9 = 12;
LABEL_14:
    WPP_SF_Dd(v8[2], v9, WPP_8ca0ecc9a63d3d47c093cf22e6bad64a_Traceguids, (unsigned int)v6, v1);
    goto LABEL_30;
  }
  WFDRegisterVMgrCallerInt(*((_QWORD *)this + 9), 4);
  *((_DWORD *)this + 14) = 1;
LABEL_23:
  started = WlanStartAP(
              *((_QWORD *)this + 8),
              *((_QWORD *)this + 9),
              (char *)this + 80,
              (char *)this + 88,
              (char *)this + 96,
              (char *)this + 104);
  if ( !started )
  {
    *((_DWORD *)this + 14) = 2;
    goto LABEL_32;
  }
  if ( started > 0 )
    v12 = (unsigned __int16)started | 0x80070000;
  else
    v12 = started;
  v1 = v12 | 0x80000000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13);
LABEL_30:
  CWcnSoftApApiWrapper::DisableSoftAp(this);
LABEL_32:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v1 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v13 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v14 + 16), 14, (unsigned int)WPP_8ca0ecc9a63d3d47c093cf22e6bad64a_Traceguids, v13, v1);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180052520  mov     [rsp+arg_8], rbx
0x180052525  mov     [rsp+arg_10], rbp
0x18005252a  push    rsi
0x18005252b  push    rdi
0x18005252c  push    r12
0x18005252e  sub     rsp, 30h
0x180052532  xor     ebx, ebx
0x180052534  mov     rdi, rcx
0x180052537  mov     [rsp+48h+pdwNegotiatedVersion], ebx
0x18005253b  mov     r10, cs:WPP_GLOBAL_Control
0x180052542  lea     r12, WPP_GLOBAL_Control
0x180052549  cmp     r10, r12
0x18005254c  jz      short loc_180052573
0x18005254e  cmp     byte ptr [r10+19h], 6
0x180052553  jb      short loc_180052573
0x180052555  lea     ecx, [rbx+1]; int
0x180052558  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18005255d  mov     rcx, [r10+10h]
0x180052561  lea     edx, [rbx+0Ah]
0x180052564  mov     r9, rax
0x180052567  lea     r8, WPP_8ca0ecc9a63d3d47c093cf22e6bad64a_Traceguids
0x18005256e  call    WPP_SF_s
0x180052573  lea     rcx, [rdi+10h]; lpCriticalSection
0x180052577  call    cs:__imp_EnterCriticalSection
0x18005257d  mov     ecx, [rdi+38h]
0x180052580  test    ecx, ecx
0x180052582  jz      short loc_180052592
0x180052584  cmp     ecx, 1
0x180052587  jz      loc_180052660
0x18005258d  jmp     loc_1800526DA
0x180052592  xor     edx, edx; pReserved
0x180052594  lea     r9, [rdi+40h]; phClientHandle
0x180052598  lea     r8, [rsp+48h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18005259d  lea     ecx, [rdx+2]; dwClientVersion
0x1800525a0  call    cs:__imp_WlanOpenHandle
0x1800525a6  test    eax, eax
0x1800525a8  jz      short loc_1800525FA
0x1800525aa  jg      short loc_1800525B0
0x1800525ac  mov     ebx, eax
0x1800525ae  jmp     short loc_1800525B9
0x1800525b0  movzx   ebx, ax
0x1800525b3  or      ebx, 80070000h
0x1800525b9  or      ebx, 80000000h
0x1800525bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800525c6  cmp     rcx, r12
0x1800525c9  jz      loc_1800526C9
0x1800525cf  cmp     byte ptr [rcx+19h], 2
0x1800525d3  jb      loc_1800526C9
0x1800525d9  mov     edx, 0Bh
0x1800525de  mov     rcx, [rcx+10h]
0x1800525e2  lea     r8, WPP_8ca0ecc9a63d3d47c093cf22e6bad64a_Traceguids
0x1800525e9  mov     r9d, eax
0x1800525ec  mov     dword ptr [rsp+48h+var_28], ebx
0x1800525f0  call    WPP_SF_Dd
0x1800525f5  jmp     loc_1800526C9
0x1800525fa  lea     r8, [rdi+48h]
0x1800525fe  mov     ecx, 1
0x180052603  lea     rdx, [rsp+48h+pdwNegotiatedVersion]
0x180052608  call    cs:__imp_WFDOpenHandleInt
0x18005260e  test    eax, eax
0x180052610  jz      short loc_180052648
0x180052612  jg      short loc_180052618
0x180052614  mov     ebx, eax
0x180052616  jmp     short loc_180052621
0x180052618  movzx   ebx, ax
0x18005261b  or      ebx, 80070000h
0x180052621  or      ebx, 80000000h
0x180052627  mov     rcx, cs:WPP_GLOBAL_Control
0x18005262e  cmp     rcx, r12
0x180052631  jz      loc_1800526C9
0x180052637  cmp     byte ptr [rcx+19h], 2
0x18005263b  jb      loc_1800526C9
0x180052641  mov     edx, 0Ch
0x180052646  jmp     short loc_1800525DE
0x180052648  mov     rcx, [rdi+48h]
0x18005264c  xor     r8d, r8d
0x18005264f  lea     edx, [r8+4]
0x180052653  call    cs:__imp_WFDRegisterVMgrCallerInt
0x180052659  mov     dword ptr [rdi+38h], 1
0x180052660  mov     rdx, [rdi+48h]
0x180052664  lea     rax, [rdi+68h]
0x180052668  lea     rcx, [rdi+60h]
0x18005266c  mov     [rsp+48h+var_20], rax
0x180052671  mov     [rsp+48h+var_28], rcx
0x180052676  lea     r9, [rdi+58h]
0x18005267a  mov     rcx, [rdi+40h]
0x18005267e  lea     r8, [rdi+50h]
0x180052682  call    cs:__imp_WlanStartAP
0x180052688  test    eax, eax
0x18005268a  jz      short loc_1800526D3
0x18005268c  jg      short loc_180052692
0x18005268e  mov     ebx, eax
0x180052690  jmp     short loc_18005269B
0x180052692  movzx   ebx, ax
0x180052695  or      ebx, 80070000h
0x18005269b  or      ebx, 80000000h
0x1800526a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800526a8  cmp     rcx, r12
0x1800526ab  jz      short loc_1800526C9
0x1800526ad  cmp     byte ptr [rcx+19h], 2
0x1800526b1  jb      short loc_1800526C9
0x1800526b3  mov     rcx, [rcx+10h]
0x1800526b7  mov     edx, 0Dh
0x1800526bc  mov     dword ptr [rsp+48h+var_20], ebx
0x1800526c0  mov     dword ptr [rsp+48h+var_28], eax
0x1800526c4  call    WPP_SF_DDd
0x1800526c9  mov     rcx, rdi; this
0x1800526cc  call    ?DisableSoftAp@CWcnSoftApApiWrapper@@QEAAXXZ; CWcnSoftApApiWrapper::DisableSoftAp(void)
0x1800526d1  jmp     short loc_1800526DA
0x1800526d3  mov     dword ptr [rdi+38h], 2
0x1800526da  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800526de  call    cs:__imp_LeaveCriticalSection
0x1800526e4  mov     r10, cs:WPP_GLOBAL_Control
0x1800526eb  cmp     r10, r12
0x1800526ee  jz      short loc_18005271F
0x1800526f0  test    ebx, ebx
0x1800526f2  js      short loc_1800526FB
0x1800526f4  cmp     byte ptr [r10+19h], 6
0x1800526f9  jb      short loc_18005271F
0x1800526fb  or      ecx, 0FFFFFFFFh; int
0x1800526fe  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180052703  mov     rcx, [r10+10h]
0x180052707  lea     r8, WPP_8ca0ecc9a63d3d47c093cf22e6bad64a_Traceguids
0x18005270e  mov     edx, 0Eh
0x180052713  mov     dword ptr [rsp+48h+var_28], ebx
0x180052717  mov     r9, rax
0x18005271a  call    WPP_SF_sd
0x18005271f  mov     rbp, [rsp+48h+arg_10]
0x180052724  mov     eax, ebx
0x180052726  mov     rbx, [rsp+48h+arg_8]
0x18005272b  add     rsp, 30h
0x18005272f  pop     r12
0x180052731  pop     rdi
0x180052732  pop     rsi
0x180052733  retn
```
