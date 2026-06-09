# CSsdpCacheEntry::HrUpdateEntry(_SSDP_REQUEST const *,int *,int *,ulong *)

- ea: `0x180006a60`
- end: `0x180006fc6`
- name: `?HrUpdateEntry@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@PEAH1PEAK@Z`
- size: `1382`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, const struct _SSDP_REQUEST *, int *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005260`

## callees

- `0x180006a60`
- `0x180006fd0`
- `0x180008190`
- `0x180008304`
- `0x1800085f0`
- `0x180008800`
- `0x180009bc0`
- `0x18000aef4`
- `0x18001fabc`
- `0x1800271fc`
- `0x18002e8ac`
- `0x180031278`
- `0x180031350`
- `0x180031a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006af9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006cdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006af9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006cdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006a87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006aa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006a87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006aa4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006b0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006b0d`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::HrUpdateEntry(
        CSsdpCacheEntry *this,
        const struct _SSDP_REQUEST *a2,
        int *a3,
        int *a4,
        unsigned int *a5)
{
  const char *v9; // rcx
  int MaxAgeFromCacheControl; // eax
  unsigned int v11; // eax
  unsigned int updated; // ebx
  LPCSTR v13; // rcx
  __int64 v14; // r8
  LPCSTR v15; // rcx
  char *v17; // r15
  LPCSTR v18; // rcx
  LPCSTR v19; // rcx
  int v20; // eax
  int v21; // [rsp+70h] [rbp+8h] BYREF
  int v22; // [rsp+78h] [rbp+10h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v22 = 0;
  v21 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v9 = *(const char **)(*((_QWORD *)a2 + 10) + 72LL);
  if ( !v9 )
  {
    updated = -2147024809;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
      goto LABEL_4;
    if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_43;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147942487LL);
LABEL_42:
    v18 = WPP_GLOBAL_Control;
LABEL_43:
    if ( v18 != (LPCSTR)&WPP_GLOBAL_Control && (v18[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v18 + 2), 34, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, updated);
    goto LABEL_4;
  }
  MaxAgeFromCacheControl = GetMaxAgeFromCacheControl(v9);
  if ( MaxAgeFromCacheControl == -1 )
  {
    updated = -2147024809;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147942487LL);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    goto LABEL_38;
  }
  v11 = CTimerBase::HrResetTimer((char *)this + 120, 1000 * MaxAgeFromCacheControl);
  *(_DWORD *)this = 0;
  updated = v11;
  if ( v11 )
    goto LABEL_42;
LABEL_4:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( updated )
    goto LABEL_38;
  *((_QWORD *)this + 33) = GetTickCount64();
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
  {
    v17 = (char *)this + 88;
    if ( (WPP_GLOBAL_Control[28] & 8) != 0 )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
        **(_QWORD **)v17,
        **((_QWORD **)a2 + 10));
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (v13[28] & 8) != 0 )
      {
        WPP_SF_ss(
          *((_QWORD *)v13 + 2),
          36,
          (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          *(_QWORD *)(*(_QWORD *)v17 + 64LL),
          *(_QWORD *)(*((_QWORD *)a2 + 10) + 64LL));
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 != (LPCSTR)&WPP_GLOBAL_Control )
      {
        if ( (v13[28] & 8) != 0 )
        {
          WPP_SF_ss(
            *((_QWORD *)v13 + 2),
            37,
            (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
            *(_QWORD *)(*(_QWORD *)v17 + 8LL),
            *(_QWORD *)(*((_QWORD *)a2 + 10) + 8LL));
          v13 = WPP_GLOBAL_Control;
        }
        if ( v13 != (LPCSTR)&WPP_GLOBAL_Control )
        {
          if ( (v13[28] & 8) != 0 )
          {
            WPP_SF_ss(
              *((_QWORD *)v13 + 2),
              38,
              (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
              *(_QWORD *)(*((_QWORD *)this + 11) + 48LL),
              *(_QWORD *)(*((_QWORD *)a2 + 10) + 48LL));
            v13 = WPP_GLOBAL_Control;
          }
          if ( v13 != (LPCSTR)&WPP_GLOBAL_Control )
          {
            if ( (v13[28] & 8) != 0 )
            {
              WPP_SF_ss(
                *((_QWORD *)v13 + 2),
                39,
                (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
                *(_QWORD *)(*((_QWORD *)this + 11) + 152LL),
                *(_QWORD *)(*((_QWORD *)a2 + 10) + 152LL));
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 != (LPCSTR)&WPP_GLOBAL_Control && (v13[28] & 8) != 0 )
              WPP_SF_ss(
                *((_QWORD *)v13 + 2),
                40,
                (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
                *((_QWORD *)this + 7),
                *((_QWORD *)a2 + 6));
          }
        }
      }
    }
  }
  if ( !(unsigned int)CompareSsdpRequest((CSsdpCacheEntry *)((char *)this + 8), a2, &v22, &v21) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
    if ( v22 || v21 )
    {
      if ( v19 != (LPCSTR)&WPP_GLOBAL_Control && (v19[28] & 8) != 0 )
        WPP_SF_qdd(*((_QWORD *)v19 + 2), (unsigned int)v22, v14, this, v22, v21);
      *a4 = 1;
      v20 = CSsdpCacheEntry::NotifyByeByeForAllAddressFamily(this);
      updated = v20;
      if ( v20 < 0 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          (unsigned int)v20);
      CSsdpCacheEntry::ClearLocationCacheEntry(this);
    }
  }
  FreeSsdpRequest((CSsdpCacheEntry *)((char *)this + 8));
  if ( (unsigned int)CopySsdpRequest((struct _NETWORK_LOCATION_INFO **)this + 1, a2) )
  {
    if ( (updated & 0x80000000) == 0 )
    {
      updated = CSsdpCacheEntry::UpdateLocationCacheEntry(this, a4, a3);
      *a5 = (*((_DWORD *)this + 27) != 0) + (*((_DWORD *)this + 28) != 0);
    }
  }
  else
  {
    updated = -2147024882;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[28] & 8) == 0 )
    {
LABEL_14:
      if ( v15 != (LPCSTR)&WPP_GLOBAL_Control && (v15[28] & 8) != 0 )
      {
        WPP_SF_qd(*((_QWORD *)v15 + 2), 45, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, this, *a4);
        v15 = WPP_GLOBAL_Control;
      }
      goto LABEL_11;
    }
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids);
LABEL_38:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
LABEL_11:
  if ( updated && v15 != (LPCSTR)&WPP_GLOBAL_Control && (v15[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v15 + 2), 46, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, updated);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  return updated;
}

```

## disassembly

```asm
0x180006a60  mov     [rsp+arg_10], rbx
0x180006a65  push    rbp
0x180006a66  push    rsi
0x180006a67  push    rdi
0x180006a68  push    r12
0x180006a6a  push    r13
0x180006a6c  push    r14
0x180006a6e  push    r15
0x180006a70  sub     rsp, 30h
0x180006a74  mov     r14, rcx
0x180006a77  mov     r13, r9
0x180006a7a  add     rcx, 0D8h; lpCriticalSection
0x180006a81  mov     r12, r8
0x180006a84  mov     rbp, rdx
0x180006a87  call    cs:__imp_EnterCriticalSection
0x180006a8e  nop     dword ptr [rax+rax+00h]
0x180006a93  xor     esi, esi
0x180006a95  lea     rcx, [r14+0D8h]; lpCriticalSection
0x180006a9c  mov     [rsp+68h+arg_8], esi
0x180006aa0  mov     [rsp+68h+arg_0], esi
0x180006aa4  call    cs:__imp_EnterCriticalSection
0x180006aab  nop     dword ptr [rax+rax+00h]
0x180006ab0  mov     rax, [rbp+50h]
0x180006ab4  lea     r15, WPP_GLOBAL_Control
0x180006abb  mov     rcx, [rax+48h]; char *
0x180006abf  test    rcx, rcx
0x180006ac2  jz      loc_180006CF3
0x180006ac8  call    ?GetMaxAgeFromCacheControl@@YAHPEBD@Z; GetMaxAgeFromCacheControl(char const *)
0x180006acd  cmp     eax, 0FFFFFFFFh
0x180006ad0  jz      loc_180006D5D
0x180006ad6  imul    edx, eax, 3E8h; DueTime
0x180006adc  lea     rcx, [r14+78h]; Parameter
0x180006ae0  call    ?HrResetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrResetTimer(ulong)
0x180006ae5  mov     [r14], esi
0x180006ae8  mov     ebx, eax
0x180006aea  test    eax, eax
0x180006aec  jnz     loc_180006D26
0x180006af2  lea     rcx, [r14+0D8h]; lpCriticalSection
0x180006af9  call    cs:__imp_LeaveCriticalSection
0x180006b00  nop     dword ptr [rax+rax+00h]
0x180006b05  test    ebx, ebx
0x180006b07  jnz     loc_180006CE7
0x180006b0d  call    cs:__imp_GetTickCount64
0x180006b14  nop     dword ptr [rax+rax+00h]
0x180006b19  mov     [r14+108h], rax
0x180006b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b27  cmp     rcx, r15
0x180006b2a  jnz     loc_180006C26
0x180006b30  lea     r9, [rsp+68h+arg_0]; int *
0x180006b35  mov     rdx, rbp; struct _SSDP_REQUEST *
0x180006b38  lea     r8, [rsp+68h+arg_8]; int *
0x180006b3d  lea     rcx, [r14+8]; struct _SSDP_REQUEST *
0x180006b41  call    ?CompareSsdpRequest@@YAHPEBU_SSDP_REQUEST@@0PEAH1@Z; CompareSsdpRequest(_SSDP_REQUEST const *,_SSDP_REQUEST const *,int *,int *)
0x180006b46  test    eax, eax
0x180006b48  jz      loc_180006EBE
0x180006b4e  lea     rcx, [r14+8]; struct _SSDP_REQUEST *
0x180006b52  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180006b57  mov     rdx, rbp; struct _SSDP_REQUEST *
0x180006b5a  lea     rcx, [r14+8]; struct _SSDP_REQUEST *
0x180006b5e  call    ?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z; CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)
0x180006b63  test    eax, eax
0x180006b65  jz      loc_180006F6F
0x180006b6b  test    ebx, ebx
0x180006b6d  jns     loc_180006BF3
0x180006b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b7a  cmp     rcx, r15
0x180006b7d  jnz     short loc_180006BB5
0x180006b7f  test    ebx, ebx
0x180006b81  jnz     loc_180006F96
0x180006b87  lea     rcx, [r14+0D8h]; lpCriticalSection
0x180006b8e  call    cs:__imp_LeaveCriticalSection
0x180006b95  nop     dword ptr [rax+rax+00h]
0x180006b9a  mov     eax, ebx
0x180006b9c  mov     rbx, [rsp+68h+arg_10]
0x180006ba4  add     rsp, 30h
0x180006ba8  pop     r15
0x180006baa  pop     r14
0x180006bac  pop     r13
0x180006bae  pop     r12
0x180006bb0  pop     rdi
0x180006bb1  pop     rsi
0x180006bb2  pop     rbp
0x180006bb3  retn
0x180006bb5  test    byte ptr [rcx+1Ch], 8
0x180006bb9  jnz     loc_180006F79
0x180006bbf  cmp     rcx, r15
0x180006bc2  jz      short loc_180006B7F
0x180006bc4  test    byte ptr [rcx+1Ch], 8
0x180006bc8  jz      short loc_180006B7F
0x180006bca  mov     eax, [r13+0]
0x180006bce  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006bd5  mov     rcx, [rcx+10h]
0x180006bd9  mov     edx, 2Dh ; '-'
0x180006bde  mov     r9, r14
0x180006be1  mov     dword ptr [rsp+68h+var_48], eax
0x180006be5  call    WPP_SF_qd
0x180006bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bf1  jmp     short loc_180006B7F
0x180006bf3  mov     r8, r12; int *
0x180006bf6  mov     rdx, r13; int *
0x180006bf9  mov     rcx, r14; this
0x180006bfc  call    ?UpdateLocationCacheEntry@CSsdpCacheEntry@@AEAAJPEAH0@Z; CSsdpCacheEntry::UpdateLocationCacheEntry(int *,int *)
0x180006c01  xor     ecx, ecx
0x180006c03  mov     ebx, eax
0x180006c05  cmp     [r14+70h], ecx
0x180006c09  setnz   cl
0x180006c0c  xor     eax, eax
0x180006c0e  cmp     [r14+6Ch], eax
0x180006c12  setnz   al
0x180006c15  add     ecx, eax
0x180006c17  mov     rax, [rsp+68h+arg_20]
0x180006c1f  mov     [rax], ecx
0x180006c21  jmp     loc_180006B73
0x180006c26  test    byte ptr [rcx+1Ch], 8
0x180006c2a  lea     r15, [r14+58h]
0x180006c2e  jnz     loc_180006D94
0x180006c34  lea     rax, WPP_GLOBAL_Control
0x180006c3b  cmp     rcx, rax
0x180006c3e  jz      short loc_180006C52
0x180006c40  test    byte ptr [rcx+1Ch], 8
0x180006c44  jnz     loc_180006DC7
0x180006c4a  mov     rsi, r15
0x180006c4d  cmp     rcx, rax
0x180006c50  jnz     short loc_180006C5E
0x180006c52  lea     r15, WPP_GLOBAL_Control
0x180006c59  jmp     loc_180006B30
0x180006c5e  test    byte ptr [rcx+1Ch], 8
0x180006c62  jnz     loc_180006E07
0x180006c68  mov     r15, rsi
0x180006c6b  cmp     rcx, rax
0x180006c6e  jz      short loc_180006C52
0x180006c70  test    byte ptr [rcx+1Ch], 8
0x180006c74  jnz     loc_180006E47
0x180006c7a  cmp     rcx, rax
0x180006c7d  jz      short loc_180006C52
0x180006c7f  test    byte ptr [rcx+1Ch], 8
0x180006c83  jnz     loc_180006E83
0x180006c89  lea     r15, WPP_GLOBAL_Control
0x180006c90  cmp     rcx, r15
0x180006c93  jz      loc_180006B30
0x180006c99  test    byte ptr [rcx+1Ch], 8
0x180006c9d  jz      loc_180006B30
0x180006ca3  mov     rax, [rbp+30h]
0x180006ca7  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006cae  mov     r9, [r14+38h]
0x180006cb2  mov     edx, 28h ; '('
0x180006cb7  mov     rcx, [rcx+10h]
0x180006cbb  mov     [rsp+68h+var_48], rax
0x180006cc0  call    WPP_SF_ss
0x180006cc5  jmp     loc_180006B30
0x180006cca  test    byte ptr [rcx+1Ch], 1
0x180006cce  jnz     loc_180006D77
0x180006cd4  lea     rcx, [r14+0D8h]; lpCriticalSection
0x180006cdb  call    cs:__imp_LeaveCriticalSection
0x180006ce2  nop     dword ptr [rax+rax+00h]
0x180006ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cee  jmp     loc_180006BBF
0x180006cf3  mov     ebx, 80070057h
0x180006cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cff  cmp     rcx, r15
0x180006d02  jz      loc_180006AF2
0x180006d08  test    byte ptr [rcx+1Ch], 1
0x180006d0c  jz      short loc_180006D2D
0x180006d0e  mov     rcx, [rcx+10h]
0x180006d12  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006d19  mov     edx, 20h ; ' '
0x180006d1e  mov     r9d, ebx
0x180006d21  call    WPP_SF_d
0x180006d26  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d2d  cmp     rcx, r15
0x180006d30  jz      loc_180006AF2
0x180006d36  test    byte ptr [rcx+1Ch], 1
0x180006d3a  jz      loc_180006AF2
0x180006d40  mov     rcx, [rcx+10h]
0x180006d44  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006d4b  mov     edx, 22h ; '"'
0x180006d50  mov     r9d, ebx
0x180006d53  call    WPP_SF_d
0x180006d58  jmp     loc_180006AF2
0x180006d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d64  mov     ebx, 80070057h
0x180006d69  cmp     rcx, r15
0x180006d6c  jz      loc_180006CD4
0x180006d72  jmp     loc_180006CCA
0x180006d77  mov     rcx, [rcx+10h]
0x180006d7b  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006d82  mov     edx, 21h ; '!'
0x180006d87  mov     r9d, ebx
0x180006d8a  call    WPP_SF_d
0x180006d8f  jmp     loc_180006CD4
0x180006d94  mov     rax, [rbp+50h]
0x180006d98  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006d9f  mov     r9, [r15]
0x180006da2  mov     edx, 23h ; '#'
0x180006da7  mov     rcx, [rcx+10h]
0x180006dab  mov     rax, [rax]
0x180006dae  mov     r9, [r9]
0x180006db1  mov     [rsp+68h+var_48], rax
0x180006db6  call    WPP_SF_ss
0x180006dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dc2  jmp     loc_180006C34
0x180006dc7  mov     rax, [rbp+50h]
0x180006dcb  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006dd2  mov     r9, [r15]
0x180006dd5  mov     edx, 24h ; '$'
0x180006dda  mov     rcx, [rcx+10h]
0x180006dde  mov     rax, [rax+40h]
0x180006de2  mov     r9, [r9+40h]
0x180006de6  mov     [rsp+68h+var_48], rax
0x180006deb  call    WPP_SF_ss
0x180006df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006df7  lea     rax, WPP_GLOBAL_Control
0x180006dfe  lea     rsi, [r14+58h]
0x180006e02  jmp     loc_180006C4D
0x180006e07  mov     rax, [rbp+50h]
0x180006e0b  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006e12  mov     r9, [r15]
0x180006e15  mov     edx, 25h ; '%'
0x180006e1a  mov     rcx, [rcx+10h]
0x180006e1e  mov     rax, [rax+8]
0x180006e22  mov     r9, [r9+8]
0x180006e26  mov     [rsp+68h+var_48], rax
0x180006e2b  call    WPP_SF_ss
0x180006e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e37  lea     rax, WPP_GLOBAL_Control
0x180006e3e  lea     r15, [r14+58h]
0x180006e42  jmp     loc_180006C6B
0x180006e47  mov     rax, [rbp+50h]
0x180006e4b  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006e52  mov     r9, [rsi]
0x180006e55  mov     edx, 26h ; '&'
0x180006e5a  mov     rcx, [rcx+10h]
0x180006e5e  mov     rax, [rax+30h]
0x180006e62  mov     r9, [r9+30h]
0x180006e66  mov     [rsp+68h+var_48], rax
0x180006e6b  call    WPP_SF_ss
0x180006e70  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e77  lea     rax, WPP_GLOBAL_Control
0x180006e7e  jmp     loc_180006C7A
0x180006e83  mov     rax, [rbp+50h]
0x180006e87  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006e8e  mov     r9, [r15]
0x180006e91  mov     edx, 27h ; '''
0x180006e96  mov     rcx, [rcx+10h]
0x180006e9a  mov     rax, [rax+98h]
0x180006ea1  mov     r9, [r9+98h]
0x180006ea8  mov     [rsp+68h+var_48], rax
0x180006ead  call    WPP_SF_ss
0x180006eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006eb9  jmp     loc_180006C89
0x180006ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ec5  cmp     rcx, r15
0x180006ec8  jz      short loc_180006EEF
0x180006eca  test    byte ptr [rcx+1Ch], 8
0x180006ece  jz      short loc_180006EEF
0x180006ed0  mov     rcx, [rcx+10h]
0x180006ed4  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006edb  mov     edx, 29h ; ')'
0x180006ee0  mov     r9, r14
0x180006ee3  call    WPP_SF_q
0x180006ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006eef  mov     edx, [rsp+68h+arg_8]
0x180006ef3  mov     eax, [rsp+68h+arg_0]
0x180006ef7  test    edx, edx
0x180006ef9  jnz     short loc_180006F03
0x180006efb  test    eax, eax
0x180006efd  jz      loc_180006B4E
0x180006f03  cmp     rcx, r15
0x180006f06  jz      short loc_180006F22
0x180006f08  test    byte ptr [rcx+1Ch], 8
0x180006f0c  jz      short loc_180006F22
0x180006f0e  mov     rcx, [rcx+10h]
0x180006f12  mov     r9, r14
0x180006f15  mov     [rsp+68h+var_40], eax
0x180006f19  mov     dword ptr [rsp+68h+var_48], edx
0x180006f1d  call    WPP_SF_qdd
0x180006f22  mov     rcx, r14; this
0x180006f25  mov     dword ptr [r13+0], 1
0x180006f2d  call    ?NotifyByeByeForAllAddressFamily@CSsdpCacheEntry@@QEAAJXZ; CSsdpCacheEntry::NotifyByeByeForAllAddressFamily(void)
0x180006f32  mov     ebx, eax
0x180006f34  test    eax, eax
0x180006f36  jns     short loc_180006F62
0x180006f38  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f3f  cmp     rcx, r15
0x180006f42  jz      short loc_180006F62
0x180006f44  test    byte ptr [rcx+1Ch], 1
0x180006f48  jz      short loc_180006F62
0x180006f4a  mov     rcx, [rcx+10h]
0x180006f4e  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006f55  mov     edx, 2Bh ; '+'
0x180006f5a  mov     r9d, eax
0x180006f5d  call    WPP_SF_d
0x180006f62  mov     rcx, r14; this
0x180006f65  call    ?ClearLocationCacheEntry@CSsdpCacheEntry@@AEAAXXZ; CSsdpCacheEntry::ClearLocationCacheEntry(void)
0x180006f6a  jmp     loc_180006B4E
0x180006f6f  mov     ebx, 8007000Eh
0x180006f74  jmp     loc_180006B73
0x180006f79  mov     rcx, [rcx+10h]
0x180006f7d  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180006f84  mov     edx, 2Ch ; ','
  ... truncated ...
```
