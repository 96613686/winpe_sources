# CSsdpCacheEntry::NotifyForAllAddressFamily(int)

- ea: `0x18000af80`
- end: `0x18000b17e`
- name: `?NotifyForAllAddressFamily@CSsdpCacheEntry@@QEAAJH@Z`
- size: `510`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000aef4`
- `0x18000bd3c`
- `0x18001f6c4`

## callees

- `0x18000af80`
- `0x18000b184`
- `0x18000b28c`
- `0x1800271fc`
- `0x18002fe28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b160`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b160`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af9c`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::NotifyForAllAddressFamily(CSsdpCacheEntry *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r14
  int v3; // edi
  int v4; // eax
  LPCSTR v5; // rcx
  _DWORD *v6; // rbx
  int v7; // eax
  LPCSTR v8; // rcx
  struct _GUID v10; // [rsp+20h] [rbp-48h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v3 = 0;
  if ( *((_DWORD *)this + 27) )
  {
    v10 = GUID_NULL;
    v3 = CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(this, (CSsdpCacheEntry *)((char *)this + 8), &v10, 0);
    if ( v3 >= 0 )
    {
      v4 = CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(
             &CSsdpNotifyRequestManager::s_instance,
             (CSsdpCacheEntry *)((char *)this + 8),
             0,
             (*((_DWORD *)this + 27) != 0) + (unsigned int)(*((_DWORD *)this + 28) != 0));
      v3 = v4;
      if ( v4 >= 0 )
        goto LABEL_7;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
        {
LABEL_8:
          if ( v5 != (LPCSTR)&WPP_GLOBAL_Control && (v5[28] & 8) != 0 )
            WPP_SF_s(
              *((_QWORD *)v5 + 2),
              22,
              WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
              *(_QWORD *)(*((_QWORD *)this + 11) + 48LL));
          goto LABEL_11;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          (unsigned int)v4);
LABEL_7:
        v5 = WPP_GLOBAL_Control;
        goto LABEL_8;
      }
    }
LABEL_11:
    *((_DWORD *)this + 27) = 0;
  }
  v6 = (_DWORD *)((char *)this + 112);
  if ( *((_DWORD *)this + 28) )
  {
    v10 = GUID_NULL;
    v3 = CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(this, (CSsdpCacheEntry *)((char *)this + 8), &v10, 1u);
    if ( v3 >= 0 )
    {
      v7 = CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(
             &CSsdpNotifyRequestManager::s_instance,
             (CSsdpCacheEntry *)((char *)this + 8),
             0,
             (*v6 != 0) + (unsigned int)(*((_DWORD *)this + 27) != 0));
      v3 = v7;
      if ( v7 >= 0 )
        goto LABEL_18;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
        {
LABEL_19:
          if ( v8 != (LPCSTR)&WPP_GLOBAL_Control && (v8[28] & 8) != 0 )
            WPP_SF_s(
              *((_QWORD *)v8 + 2),
              24,
              WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
              *(_QWORD *)(*((_QWORD *)this + 11) + 48LL));
          goto LABEL_22;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          (unsigned int)v7);
        v6 = (_DWORD *)((char *)this + 112);
LABEL_18:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_19;
      }
    }
LABEL_22:
    *v6 = 0;
  }
  if ( v3 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, (unsigned int)v3);
  LeaveCriticalSection(v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000af80  push    rbx
0x18000af82  push    rbp
0x18000af83  push    rsi
0x18000af84  push    rdi
0x18000af85  push    r12
0x18000af87  push    r13
0x18000af89  push    r14
0x18000af8b  sub     rsp, 30h
0x18000af8f  lea     r14, [rcx+0D8h]
0x18000af96  mov     rsi, rcx
0x18000af99  mov     rcx, r14; lpCriticalSection
0x18000af9c  call    cs:__imp_EnterCriticalSection
0x18000afa3  nop     dword ptr [rax+rax+00h]
0x18000afa8  xor     edi, edi
0x18000afaa  lea     rbp, [rsi+8]
0x18000afae  lea     r12, WPP_GLOBAL_Control
0x18000afb5  lea     r13, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000afbc  cmp     [rsi+6Ch], edi
0x18000afbf  jz      loc_18000B071
0x18000afc5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000afcc  xor     r9d, r9d; unsigned int
0x18000afcf  lea     r8, [rsp+68h+var_48]; struct _GUID
0x18000afd4  mov     rdx, rbp; struct _SSDP_REQUEST *
0x18000afd7  mov     rcx, rsi; this
0x18000afda  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x18000afe0  call    ?ComposeSsdpRequestFromNetworkLocation@CSsdpCacheEntry@@AEAAJPEAU_SSDP_REQUEST@@U_GUID@@K@Z; CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(_SSDP_REQUEST *,_GUID,ulong)
0x18000afe5  mov     edi, eax
0x18000afe7  test    eax, eax
0x18000afe9  js      short loc_18000B06A
0x18000afeb  xor     r9d, r9d
0x18000afee  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; lpCriticalSection
0x18000aff5  cmp     [rsi+70h], r9d
0x18000aff9  mov     rdx, rbp; struct _SSDP_REQUEST *
0x18000affc  setnz   r9b
0x18000b000  xor     eax, eax
0x18000b002  cmp     [rsi+6Ch], eax
0x18000b005  setnz   al
0x18000b008  xor     r8d, r8d; int
0x18000b00b  add     r9d, eax; unsigned int
0x18000b00e  call    ?HrCheckListNotifyForAliveOrByebye@CSsdpNotifyRequestManager@@QEAAJPEBU_SSDP_REQUEST@@HK@Z; CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(_SSDP_REQUEST const *,int,ulong)
0x18000b013  mov     edi, eax
0x18000b015  test    eax, eax
0x18000b017  jns     short loc_18000B03F
0x18000b019  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b020  cmp     rcx, r12
0x18000b023  jz      short loc_18000B06A
0x18000b025  test    byte ptr [rcx+1Ch], 1
0x18000b029  jz      short loc_18000B046
0x18000b02b  mov     rcx, [rcx+10h]
0x18000b02f  mov     edx, 15h
0x18000b034  mov     r9d, eax
0x18000b037  mov     r8, r13
0x18000b03a  call    WPP_SF_d
0x18000b03f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b046  cmp     rcx, r12
0x18000b049  jz      short loc_18000B06A
0x18000b04b  test    byte ptr [rcx+1Ch], 8
0x18000b04f  jz      short loc_18000B06A
0x18000b051  mov     r9, [rsi+58h]
0x18000b055  mov     edx, 16h
0x18000b05a  mov     rcx, [rcx+10h]
0x18000b05e  mov     r8, r13
0x18000b061  mov     r9, [r9+30h]
0x18000b065  call    WPP_SF_s
0x18000b06a  mov     dword ptr [rsi+6Ch], 0
0x18000b071  lea     rbx, [rsi+70h]
0x18000b075  cmp     dword ptr [rbx], 0
0x18000b078  jz      loc_18000B133
0x18000b07e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000b085  mov     r9d, 1; unsigned int
0x18000b08b  lea     r8, [rsp+68h+var_48]; struct _GUID
0x18000b090  mov     rdx, rbp; struct _SSDP_REQUEST *
0x18000b093  mov     rcx, rsi; this
0x18000b096  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x18000b09c  call    ?ComposeSsdpRequestFromNetworkLocation@CSsdpCacheEntry@@AEAAJPEAU_SSDP_REQUEST@@U_GUID@@K@Z; CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(_SSDP_REQUEST *,_GUID,ulong)
0x18000b0a1  mov     edi, eax
0x18000b0a3  test    eax, eax
0x18000b0a5  js      loc_18000B12D
0x18000b0ab  xor     r9d, r9d
0x18000b0ae  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; lpCriticalSection
0x18000b0b5  cmp     [rsi+6Ch], r9d
0x18000b0b9  mov     rdx, rbp; struct _SSDP_REQUEST *
0x18000b0bc  setnz   r9b
0x18000b0c0  xor     eax, eax
0x18000b0c2  cmp     [rbx], eax
0x18000b0c4  setnz   al
0x18000b0c7  xor     r8d, r8d; int
0x18000b0ca  add     r9d, eax; unsigned int
0x18000b0cd  call    ?HrCheckListNotifyForAliveOrByebye@CSsdpNotifyRequestManager@@QEAAJPEBU_SSDP_REQUEST@@HK@Z; CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(_SSDP_REQUEST const *,int,ulong)
0x18000b0d2  mov     edi, eax
0x18000b0d4  test    eax, eax
0x18000b0d6  jns     short loc_18000B102
0x18000b0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0df  cmp     rcx, r12
0x18000b0e2  jz      short loc_18000B12D
0x18000b0e4  test    byte ptr [rcx+1Ch], 1
0x18000b0e8  jz      short loc_18000B109
0x18000b0ea  mov     rcx, [rcx+10h]
0x18000b0ee  mov     edx, 17h
0x18000b0f3  mov     r9d, eax
0x18000b0f6  mov     r8, r13
0x18000b0f9  call    WPP_SF_d
0x18000b0fe  lea     rbx, [rsi+70h]
0x18000b102  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b109  cmp     rcx, r12
0x18000b10c  jz      short loc_18000B12D
0x18000b10e  test    byte ptr [rcx+1Ch], 8
0x18000b112  jz      short loc_18000B12D
0x18000b114  mov     r9, [rsi+58h]
0x18000b118  mov     edx, 18h
0x18000b11d  mov     rcx, [rcx+10h]
0x18000b121  mov     r8, r13
0x18000b124  mov     r9, [r9+30h]
0x18000b128  call    WPP_SF_s
0x18000b12d  mov     dword ptr [rbx], 0
0x18000b133  test    edi, edi
0x18000b135  jz      short loc_18000B15D
0x18000b137  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b13e  cmp     rcx, r12
0x18000b141  jz      short loc_18000B15D
0x18000b143  test    byte ptr [rcx+1Ch], 1
0x18000b147  jz      short loc_18000B15D
0x18000b149  mov     rcx, [rcx+10h]
0x18000b14d  mov     edx, 19h
0x18000b152  mov     r9d, edi
0x18000b155  mov     r8, r13
0x18000b158  call    WPP_SF_d
0x18000b15d  mov     rcx, r14; lpCriticalSection
0x18000b160  call    cs:__imp_LeaveCriticalSection
0x18000b167  nop     dword ptr [rax+rax+00h]
0x18000b16c  mov     eax, edi
0x18000b16e  add     rsp, 30h
0x18000b172  pop     r14
0x18000b174  pop     r13
0x18000b176  pop     r12
0x18000b178  pop     rdi
0x18000b179  pop     rsi
0x18000b17a  pop     rbp
0x18000b17b  pop     rbx
0x18000b17c  retn
```
