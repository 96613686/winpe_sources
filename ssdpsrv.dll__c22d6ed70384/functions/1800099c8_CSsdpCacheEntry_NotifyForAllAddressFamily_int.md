# CSsdpCacheEntry::NotifyForAllAddressFamily(int)

- ea: `0x1800099c8`
- end: `0x180009bb9`
- name: `?NotifyForAllAddressFamily@CSsdpCacheEntry@@QEAAJH@Z`
- size: `497`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000993c`
- `0x18000a590`
- `0x18001e1d4`

## callees

- `0x1800099c8`
- `0x180009bc0`
- `0x180009cac`
- `0x1800255a8`
- `0x18002dcf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ba2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ba2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800099e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800099e4`

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
0x1800099c8  push    rbx
0x1800099ca  push    rbp
0x1800099cb  push    rsi
0x1800099cc  push    rdi
0x1800099cd  push    r12
0x1800099cf  push    r13
0x1800099d1  push    r14
0x1800099d3  sub     rsp, 30h
0x1800099d7  lea     r14, [rcx+0D8h]
0x1800099de  mov     rsi, rcx
0x1800099e1  mov     rcx, r14; lpCriticalSection
0x1800099e4  call    cs:__imp_EnterCriticalSection
0x1800099ea  xor     edi, edi
0x1800099ec  lea     rbp, [rsi+8]
0x1800099f0  lea     r12, WPP_GLOBAL_Control
0x1800099f7  lea     r13, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x1800099fe  cmp     [rsi+6Ch], edi
0x180009a01  jz      loc_180009AB3
0x180009a07  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180009a0e  xor     r9d, r9d; unsigned int
0x180009a11  lea     r8, [rsp+68h+var_48]; struct _GUID
0x180009a16  mov     rdx, rbp; struct _SSDP_REQUEST *
0x180009a19  mov     rcx, rsi; this
0x180009a1c  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x180009a22  call    ?ComposeSsdpRequestFromNetworkLocation@CSsdpCacheEntry@@AEAAJPEAU_SSDP_REQUEST@@U_GUID@@K@Z; CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(_SSDP_REQUEST *,_GUID,ulong)
0x180009a27  mov     edi, eax
0x180009a29  test    eax, eax
0x180009a2b  js      short loc_180009AAC
0x180009a2d  xor     r9d, r9d
0x180009a30  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; lpCriticalSection
0x180009a37  cmp     [rsi+70h], r9d
0x180009a3b  mov     rdx, rbp; struct _SSDP_REQUEST *
0x180009a3e  setnz   r9b
0x180009a42  xor     eax, eax
0x180009a44  cmp     [rsi+6Ch], eax
0x180009a47  setnz   al
0x180009a4a  xor     r8d, r8d; int
0x180009a4d  add     r9d, eax; unsigned int
0x180009a50  call    ?HrCheckListNotifyForAliveOrByebye@CSsdpNotifyRequestManager@@QEAAJPEBU_SSDP_REQUEST@@HK@Z; CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(_SSDP_REQUEST const *,int,ulong)
0x180009a55  mov     edi, eax
0x180009a57  test    eax, eax
0x180009a59  jns     short loc_180009A81
0x180009a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a62  cmp     rcx, r12
0x180009a65  jz      short loc_180009AAC
0x180009a67  test    byte ptr [rcx+1Ch], 1
0x180009a6b  jz      short loc_180009A88
0x180009a6d  mov     rcx, [rcx+10h]
0x180009a71  mov     edx, 15h
0x180009a76  mov     r9d, eax
0x180009a79  mov     r8, r13
0x180009a7c  call    WPP_SF_d
0x180009a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a88  cmp     rcx, r12
0x180009a8b  jz      short loc_180009AAC
0x180009a8d  test    byte ptr [rcx+1Ch], 8
0x180009a91  jz      short loc_180009AAC
0x180009a93  mov     r9, [rsi+58h]
0x180009a97  mov     edx, 16h
0x180009a9c  mov     rcx, [rcx+10h]
0x180009aa0  mov     r8, r13
0x180009aa3  mov     r9, [r9+30h]
0x180009aa7  call    WPP_SF_s
0x180009aac  mov     dword ptr [rsi+6Ch], 0
0x180009ab3  lea     rbx, [rsi+70h]
0x180009ab7  cmp     dword ptr [rbx], 0
0x180009aba  jz      loc_180009B75
0x180009ac0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180009ac7  mov     r9d, 1; unsigned int
0x180009acd  lea     r8, [rsp+68h+var_48]; struct _GUID
0x180009ad2  mov     rdx, rbp; struct _SSDP_REQUEST *
0x180009ad5  mov     rcx, rsi; this
0x180009ad8  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x180009ade  call    ?ComposeSsdpRequestFromNetworkLocation@CSsdpCacheEntry@@AEAAJPEAU_SSDP_REQUEST@@U_GUID@@K@Z; CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(_SSDP_REQUEST *,_GUID,ulong)
0x180009ae3  mov     edi, eax
0x180009ae5  test    eax, eax
0x180009ae7  js      loc_180009B6F
0x180009aed  xor     r9d, r9d
0x180009af0  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; lpCriticalSection
0x180009af7  cmp     [rsi+6Ch], r9d
0x180009afb  mov     rdx, rbp; struct _SSDP_REQUEST *
0x180009afe  setnz   r9b
0x180009b02  xor     eax, eax
0x180009b04  cmp     [rbx], eax
0x180009b06  setnz   al
0x180009b09  xor     r8d, r8d; int
0x180009b0c  add     r9d, eax; unsigned int
0x180009b0f  call    ?HrCheckListNotifyForAliveOrByebye@CSsdpNotifyRequestManager@@QEAAJPEBU_SSDP_REQUEST@@HK@Z; CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(_SSDP_REQUEST const *,int,ulong)
0x180009b14  mov     edi, eax
0x180009b16  test    eax, eax
0x180009b18  jns     short loc_180009B44
0x180009b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b21  cmp     rcx, r12
0x180009b24  jz      short loc_180009B6F
0x180009b26  test    byte ptr [rcx+1Ch], 1
0x180009b2a  jz      short loc_180009B4B
0x180009b2c  mov     rcx, [rcx+10h]
0x180009b30  mov     edx, 17h
0x180009b35  mov     r9d, eax
0x180009b38  mov     r8, r13
0x180009b3b  call    WPP_SF_d
0x180009b40  lea     rbx, [rsi+70h]
0x180009b44  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b4b  cmp     rcx, r12
0x180009b4e  jz      short loc_180009B6F
0x180009b50  test    byte ptr [rcx+1Ch], 8
0x180009b54  jz      short loc_180009B6F
0x180009b56  mov     r9, [rsi+58h]
0x180009b5a  mov     edx, 18h
0x180009b5f  mov     rcx, [rcx+10h]
0x180009b63  mov     r8, r13
0x180009b66  mov     r9, [r9+30h]
0x180009b6a  call    WPP_SF_s
0x180009b6f  mov     dword ptr [rbx], 0
0x180009b75  test    edi, edi
0x180009b77  jz      short loc_180009B9F
0x180009b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b80  cmp     rcx, r12
0x180009b83  jz      short loc_180009B9F
0x180009b85  test    byte ptr [rcx+1Ch], 1
0x180009b89  jz      short loc_180009B9F
0x180009b8b  mov     rcx, [rcx+10h]
0x180009b8f  mov     edx, 19h
0x180009b94  mov     r9d, edi
0x180009b97  mov     r8, r13
0x180009b9a  call    WPP_SF_d
0x180009b9f  mov     rcx, r14; lpCriticalSection
0x180009ba2  call    cs:__imp_LeaveCriticalSection
0x180009ba8  mov     eax, edi
0x180009baa  add     rsp, 30h
0x180009bae  pop     r14
0x180009bb0  pop     r13
0x180009bb2  pop     r12
0x180009bb4  pop     rdi
0x180009bb5  pop     rsi
0x180009bb6  pop     rbp
0x180009bb7  pop     rbx
0x180009bb8  retn
```
