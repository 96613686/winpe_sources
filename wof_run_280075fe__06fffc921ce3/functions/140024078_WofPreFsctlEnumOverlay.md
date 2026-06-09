# WofPreFsctlEnumOverlay

- ea: `0x140024078`
- end: `0x1400243c5`
- name: `WofPreFsctlEnumOverlay`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1400346f0`

## callees

- `0x1400014d0`
- `0x14000dc88`
- `0x14000e49c`
- `0x14000e578`
- `0x14000e6c8`
- `0x14000e7d8`
- `0x14000e8d4`
- `0x14000f45c`
- `0x140011590`
- `0x140011640`
- `0x140023030`
- `0x140024078`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140024127`
- `ntoskrnl!ProbeForRead` at `0x140024127`
- `ntoskrnl!ProbeForWrite` at `0x140024145`
- `ntoskrnl!ProbeForWrite` at `0x140024145`
- `FLTMGR!FltReleaseContext` at `0x140024390`
- `FLTMGR!FltReleaseContext` at `0x140024390`

## pseudocode

```c
__int64 __fastcall WofPreFsctlEnumOverlay(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  void *v6; // rsi
  unsigned int v7; // r15d
  __int64 v8; // rax
  char *v9; // rbx
  unsigned int v10; // r13d
  int IfrLog; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v15; // ebx
  __int64 ULong64FromUser; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  int VolumeContext; // eax
  __int64 v20; // r8
  int v21; // eax
  int v22; // edx
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rcx
  __int64 (__fastcall *v26)(char *, char *, _QWORD, volatile void *); // r10
  int v27; // eax
  char v28; // dl
  int v29; // edx
  int v30; // r9d
  int v31; // edx
  int v32; // r8d
  int v33; // r9d
  int v34; // eax
  int v35; // r9d
  int v36; // edx
  char v38; // [rsp+28h] [rbp-70h]
  __int64 v39; // [rsp+40h] [rbp-58h] BYREF
  char *v40; // [rsp+48h] [rbp-50h]
  volatile void *Address; // [rsp+50h] [rbp-48h]
  volatile void *v42; // [rsp+58h] [rbp-40h]
  char *v43; // [rsp+60h] [rbp-38h]
  unsigned int Length; // [rsp+B0h] [rbp+18h]

  v39 = 0;
  v6 = 0;
  v40 = 0;
  v7 = 5;
  v8 = *(_QWORD *)(a1 + 16);
  Address = *(volatile void **)(v8 + 56);
  v42 = Address;
  Length = *(_DWORD *)(v8 + 24);
  v9 = *(char **)(v8 + 48);
  v43 = v9;
  v10 = *(_DWORD *)(v8 + 32);
  if ( v10 < 8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      IfrLog = WofGetIfrLog(&WPP_RECORDER_INITIALIZED, a2, a3, a4);
      WPP_RECORDER_SF_Ld(IfrLog, v12, v13, v14);
    }
    v15 = -1073741811;
    v7 = 4;
    goto LABEL_29;
  }
  if ( *(_BYTE *)(a1 + 80)
    && (ProbeForRead(v9, *(unsigned int *)(v8 + 32), 1u), ProbeForWrite(Address, Length, 1u), *(_BYTE *)(a1 + 80)) )
  {
    ULong64FromUser = RtlReadULong64FromUser(v9);
    v39 = ULong64FromUser;
  }
  else
  {
    RtlCopyVolatileMemory(&v39, v9, 8u);
    LODWORD(ULong64FromUser) = v39;
  }
  if ( (_DWORD)ULong64FromUser == 1
    && HIDWORD(v39) < 4
    && *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * HIDWORD(v39)) )
  {
    VolumeContext = WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24));
    if ( VolumeContext < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v21 = WofGetIfrLog(&WPP_RECORDER_INITIALIZED, (unsigned int)VolumeContext, v20, 32);
        WPP_RECORDER_SF_qdd(v21, v22, v23, v24);
      }
      v15 = 0;
      goto LABEL_16;
    }
    v7 = 4;
    v25 = 424LL * HIDWORD(v39);
    v26 = *(__int64 (__fastcall **)(char *, char *, _QWORD, volatile void *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                            + v25
                                                                            + 72);
    if ( !v26 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = -1073741637;
      }
      else
      {
        v27 = WofGetIfrLog(&WPP_RECORDER_INITIALIZED, HIDWORD(v39), v20, 33);
        v15 = -1073741637;
        v38 = v28;
        LOBYTE(v29) = 3;
        WPP_RECORDER_SF_dd(v27, v29, 7, v30, (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids, v38, 187);
      }
LABEL_16:
      v6 = v40;
      goto LABEL_29;
    }
    v6 = v40;
    v15 = v26(
            &v40[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v25 + 20)],
            v9 + 8,
            v10 - 8,
            Address);
    if ( v15 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Zd(WPP_GLOBAL_Control->DeviceExtension, v31, v32, v33, Length, (__int64)v6 + 64, v15);
    if ( v15 == -1073741789 )
      v15 = -2147483643;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v34 = WofGetIfrLog(&WPP_RECORDER_INITIALIZED, v17, v18, 31);
      LOBYTE(v36) = 3;
      WPP_RECORDER_SF_d(v34, v36, v35 - 24, v35, (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids, SBYTE4(v39));
    }
    v15 = 0;
  }
LABEL_29:
  if ( v6 )
    FltReleaseContext(v6);
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 24) = v15;
  return v7;
}

```

## disassembly

```asm
0x140024078  mov     rax, rsp
0x14002407b  mov     [rax+10h], rbx
0x14002407f  mov     [rax+18h], r8
0x140024083  mov     [rax+8], rcx
0x140024087  push    rsi
0x140024088  push    r12
0x14002408a  push    r13
0x14002408c  push    r14
0x14002408e  push    r15
0x140024090  sub     rsp, 70h
0x140024094  mov     r12, rdx
0x140024097  mov     r14, rcx
0x14002409a  mov     qword ptr [rax-58h], 0
0x1400240a2  mov     dword ptr [rax+20h], 0
0x1400240a9  xor     esi, esi
0x1400240ab  mov     [rax-50h], rsi
0x1400240af  lea     r15d, [rsi+5]
0x1400240b3  mov     rax, [rcx+10h]
0x1400240b7  mov     rcx, [rax+38h]
0x1400240bb  mov     [rsp+98h+Address], rcx
0x1400240c0  mov     [rsp+98h+var_40], rcx
0x1400240c5  mov     ecx, [rax+18h]
0x1400240c8  mov     dword ptr [rsp+98h+Length], ecx
0x1400240cf  mov     rbx, [rax+30h]
0x1400240d3  mov     [rsp+98h+var_38], rbx
0x1400240d8  mov     r13d, [rax+20h]
0x1400240dc  cmp     r13d, 8
0x1400240e0  jnb     short loc_140024114
0x1400240e2  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400240e9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400240f0  jz      short loc_140024104
0x1400240f2  call    WofGetIfrLog
0x1400240f7  mov     rcx, rax
0x1400240fa  mov     dword ptr [rsp+98h+var_70], r13d
0x1400240ff  call    WPP_RECORDER_SF_Ld
0x140024104  mov     ebx, 0C000000Dh
0x140024109  mov     r15d, 4
0x14002410f  jmp     loc_140024388
0x140024114  cmp     byte ptr [r14+50h], 0
0x140024119  jz      short loc_140024167
0x14002411b  mov     rdx, r13; Length
0x14002411e  mov     r8d, 1; Alignment
0x140024124  mov     rcx, rbx; Address
0x140024127  call    cs:__imp_ProbeForRead
0x14002412e  nop     dword ptr [rax+rax+00h]
0x140024133  mov     edx, dword ptr [rsp+98h+Length]; Length
0x14002413a  mov     r8d, 1; Alignment
0x140024140  mov     rcx, [rsp+98h+Address]; Address
0x140024145  call    cs:__imp_ProbeForWrite
0x14002414c  nop     dword ptr [rax+rax+00h]
0x140024151  cmp     byte ptr [r14+50h], 0
0x140024156  jz      short loc_140024167
0x140024158  mov     rcx, rbx
0x14002415b  call    RtlReadULong64FromUser
0x140024160  mov     [rsp+98h+var_58], rax
0x140024165  jmp     short loc_14002417F
0x140024167  mov     r8d, 8; Size
0x14002416d  mov     rdx, rbx; Src
0x140024170  lea     rcx, [rsp+98h+var_58]; void *
0x140024175  call    RtlCopyVolatileMemory
0x14002417a  mov     rax, [rsp+98h+var_58]
0x14002417f  cmp     eax, 1
0x140024182  jnz     loc_1400242FE
0x140024188  cmp     dword ptr [rsp+98h+var_58+4], 4
0x14002418d  jnb     loc_1400242FE
0x140024193  mov     eax, dword ptr [rsp+98h+var_58+4]
0x140024197  imul    rcx, rax, 1A8h
0x14002419e  lea     rax, WPP_MAIN_CB.Queue+10h
0x1400241a5  cmp     byte ptr [rcx+rax], 0
0x1400241a9  jz      loc_1400242FE
0x1400241af  lea     rdx, [rsp+98h+var_50]
0x1400241b4  mov     rcx, [r12+18h]; Instance
0x1400241b9  call    WofGetVolumeContext
0x1400241be  mov     edx, eax
0x1400241c0  test    eax, eax
0x1400241c2  jns     short loc_140024209
0x1400241c4  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400241cb  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400241d2  jz      short loc_1400241FD
0x1400241d4  mov     r9d, 20h ; ' '
0x1400241da  call    WofGetIfrLog
0x1400241df  mov     rcx, rax
0x1400241e2  mov     [rsp+98h+var_60], edx
0x1400241e6  mov     eax, dword ptr [rsp+98h+var_58+4]
0x1400241ea  mov     dword ptr [rsp+98h+var_68], eax
0x1400241ee  mov     rax, [r12+18h]
0x1400241f3  mov     [rsp+98h+var_70], rax
0x1400241f8  call    WPP_RECORDER_SF_qdd
0x1400241fd  xor     ebx, ebx
0x1400241ff  mov     rsi, [rsp+98h+var_50]
0x140024204  jmp     loc_140024388
0x140024209  mov     r15d, 4
0x14002420f  mov     edx, dword ptr [rsp+98h+var_58+4]
0x140024213  imul    rcx, rdx, 1A8h
0x14002421a  lea     rax, WPP_MAIN_CB.Queue+10h
0x140024221  mov     r10, [rcx+rax+48h]
0x140024226  test    r10, r10
0x140024229  jnz     short loc_140024274
0x14002422b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140024232  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140024239  jz      short loc_14002426D
0x14002423b  lea     r9d, [r15+1Dh]
0x14002423f  call    WofGetIfrLog
0x140024244  mov     rcx, rax
0x140024247  mov     ebx, 0C00000BBh
0x14002424c  mov     dword ptr [rsp+98h+var_68], ebx
0x140024250  mov     dword ptr [rsp+98h+var_70], edx
0x140024254  lea     rax, WPP_dcfac5c580c33e55513b631fbc558444_Traceguids
0x14002425b  mov     [rsp+98h+var_78], rax
0x140024260  lea     r8d, [r15+3]
0x140024264  mov     dl, 3
0x140024266  call    WPP_RECORDER_SF_dd
0x14002426b  jmp     short loc_1400241FF
0x14002426d  mov     ebx, 0C00000BBh
0x140024272  jmp     short loc_1400241FF
0x140024274  lea     r8d, [r13-8]
0x140024278  lea     rdx, [rbx+8]
0x14002427c  mov     ecx, [rcx+rax+14h]
0x140024280  mov     rsi, [rsp+98h+var_50]
0x140024285  add     rcx, rsi
0x140024288  lea     rax, [rsp+98h+arg_18]
0x140024290  mov     [rsp+98h+var_68], rax
0x140024295  mov     al, [r14+50h]
0x140024299  mov     byte ptr [rsp+98h+var_70], al
0x14002429d  mov     eax, dword ptr [rsp+98h+Length]
0x1400242a4  mov     dword ptr [rsp+98h+var_78], eax
0x1400242a8  mov     r9, [rsp+98h+Address]
0x1400242ad  mov     rax, r10
0x1400242b0  call    _guard_dispatch_icall
0x1400242b5  mov     ebx, eax
0x1400242b7  test    eax, eax
0x1400242b9  jns     short loc_1400242E8
0x1400242bb  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400242c2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400242c9  jz      short loc_1400242E8
0x1400242cb  lea     rax, [rsi+40h]
0x1400242cf  mov     dword ptr [rsp+98h+var_68], ebx
0x1400242d3  mov     [rsp+98h+var_70], rax
0x1400242d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400242df  mov     rcx, [rcx+40h]
0x1400242e3  call    WPP_RECORDER_SF_Zd
0x1400242e8  cmp     ebx, 0C0000023h
0x1400242ee  jnz     loc_140024388
0x1400242f4  mov     ebx, 80000005h
0x1400242f9  jmp     loc_140024388
0x1400242fe  lea     rcx, WPP_RECORDER_INITIALIZED
0x140024305  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002430c  jz      short loc_14002433B
0x14002430e  mov     r9d, 1Fh
0x140024314  call    WofGetIfrLog
0x140024319  mov     rcx, rax
0x14002431c  mov     eax, dword ptr [rsp+98h+var_58+4]
0x140024320  mov     dword ptr [rsp+98h+var_70], eax
0x140024324  lea     rax, WPP_dcfac5c580c33e55513b631fbc558444_Traceguids
0x14002432b  mov     [rsp+98h+var_78], rax
0x140024330  lea     r8d, [r9-18h]
0x140024334  mov     dl, 3
0x140024336  call    WPP_RECORDER_SF_d
0x14002433b  xor     ebx, ebx
0x14002433d  jmp     short loc_140024388
0x14002433f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140024346  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002434d  jz      short loc_140024370
0x14002434f  call    WofGetIfrLog
0x140024354  mov     rcx, rax
0x140024357  mov     rax, [rsp+98h+var_40]
0x14002435c  mov     [rsp+98h+var_68], rax
0x140024361  mov     rax, [rsp+98h+var_38]
0x140024366  mov     [rsp+98h+var_70], rax
0x14002436b  call    WPP_RECORDER_SF_qqd
0x140024370  mov     ebx, 0C00000E8h
0x140024375  mov     r15d, 4
0x14002437b  mov     r14, [rsp+98h+arg_0]
0x140024383  mov     rsi, [rsp+98h+var_50]
0x140024388  test    rsi, rsi
0x14002438b  jz      short loc_14002439C
0x14002438d  mov     rcx, rsi; Context
0x140024390  call    cs:__imp_FltReleaseContext
0x140024397  nop     dword ptr [rax+rax+00h]
0x14002439c  mov     ecx, [rsp+98h+arg_18]
0x1400243a3  mov     [r14+20h], rcx
0x1400243a7  mov     [r14+18h], ebx
0x1400243ab  mov     eax, r15d
0x1400243ae  mov     rbx, [rsp+98h+arg_8]
0x1400243b6  add     rsp, 70h
0x1400243ba  pop     r15
0x1400243bc  pop     r14
0x1400243be  pop     r13
0x1400243c0  pop     r12
0x1400243c2  pop     rsi
0x1400243c3  retn
```
