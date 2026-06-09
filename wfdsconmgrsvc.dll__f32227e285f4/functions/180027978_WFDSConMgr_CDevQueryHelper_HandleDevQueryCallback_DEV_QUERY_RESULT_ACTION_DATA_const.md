# WFDSConMgr::CDevQueryHelper::HandleDevQueryCallback(_DEV_QUERY_RESULT_ACTION_DATA const *)

- ea: `0x180027978`
- end: `0x180027e4e`
- name: `?HandleDevQueryCallback@CDevQueryHelper@WFDSConMgr@@AEAAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z`
- size: `1238`
- prototype: `void __fastcall(WFDSConMgr::CDevQueryHelper *__hidden this, const struct _DEV_QUERY_RESULT_ACTION_DATA *)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x180025670`

## callees

- `0x180002ffc`
- `0x180004260`
- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x18000adcc`
- `0x18001a928`
- `0x18001b0b8`
- `0x180024090`
- `0x180027978`
- `0x180028238`
- `0x180029208`
- `0x18005c888`
- `0x18005dd90`
- `0x180060824`
- `0x18006088c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027a05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027e2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027a05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027e2f`

## string_xrefs

- `0x180027a5c`: `updated`
- `0x180027b63`: `DafDevPropertyCopy failed`
- `0x180027c0f`: `DafDevPropertyCopy failed (merging old)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WFDSConMgr::CDevQueryHelper::HandleDevQueryCallback(
        WFDSConMgr::CDevQueryHelper *this,
        const struct _DEV_QUERY_RESULT_ACTION_DATA *a2)
{
  WFDSConMgr::CDevQueryHelper *v3; // rdi
  const wchar_t *v4; // r8
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r12
  char *v9; // r13
  int v10; // r9d
  __int64 i; // rbx
  int v12; // eax
  __int64 j; // r15
  __int64 v14; // rax
  int v15; // eax
  char *v16; // rax
  PVOID *v17; // rcx
  const WFDSConMgr::CException *v18; // rbx
  WFDSConMgr::CDevQueryHelper *v19; // rdi
  __int64 v20; // rax
  WFDSConMgr::CDevQueryHelper *v21; // rbx
  WFDSConMgr::CDevQueryHelper *v22; // rbx
  __int64 v23; // [rsp+30h] [rbp-78h] BYREF
  const WFDSConMgr::CException *v24; // [rsp+38h] [rbp-70h] BYREF
  const std::exception *v25; // [rsp+40h] [rbp-68h] BYREF
  int v26; // [rsp+48h] [rbp-60h] BYREF
  char *v27; // [rsp+50h] [rbp-58h]
  _OWORD v28[4]; // [rsp+60h] [rbp-48h] BYREF
  char v30; // [rsp+C0h] [rbp+18h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+C8h] [rbp+20h] BYREF

  v3 = this;
  v30 = 0;
  WFDSConMgr::CriticalSection::Lock((char *)this + 176, &lpCriticalSection);
  if ( (unsigned int)(*((_DWORD *)v3 + 88) - 2) > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, v3);
    }
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
    return;
  }
  try
  {
    if ( *(_DWORD *)a2 )
    {
      if ( (unsigned int)(*(_DWORD *)a2 - 1) < 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v4 = L"added";
          if ( *(_DWORD *)a2 != 1 )
            v4 = (const wchar_t *)L"updated";
          WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v4, *((_QWORD *)a2 + 2));
        }
        if ( !*((_BYTE *)v3 + 125) )
          goto LABEL_20;
        if ( WFDSConMgr::CDevQueryHelper::IsUpdateForInterfaceQueryRelevant(v3, a2) )
        {
          v5 = std::_WChar_traits<unsigned short>::length(*((_QWORD *)a2 + 2));
          std::wstring::_Assign<unsigned short>((char *)v3 + 56, v6, v5);
LABEL_20:
          if ( *(_DWORD *)a2 == 1 )
          {
            *((_DWORD *)v3 + 32) = 0;
            v7 = *((_QWORD *)v3 + 18);
            *((_QWORD *)v3 + 18) = 0;
            if ( v7 )
            {
              v23 = v7;
              DafDevPropertyListFree((char *)v3 + 136, &v23);
            }
          }
          v8 = (unsigned int)(*((_DWORD *)v3 + 32) + *((_DWORD *)a2 + 6));
          v9 = (char *)operator new[](48 * v8);
          v26 = v8;
          v27 = v9;
          memset_0(v9, 0, 48 * v8);
          for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 6); i = (unsigned int)(i + 1) )
          {
            v12 = DafDevPropertyCopy(*((_QWORD *)a2 + 4) + 48 * i, &v9[48 * i]);
            if ( v12 < 0 )
              WFDSConMgr::CException::Throw(
                v12,
                "WFDSConMgr::CDevQueryHelper::HandleDevQueryCallback",
                "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\devqueryhelper.cpp",
                140,
                L"DafDevPropertyCopy failed",
                v3);
          }
          for ( j = 0;
                (unsigned int)j < *((_DWORD *)v3 + 32) && (unsigned int)i < (unsigned int)v8;
                j = (unsigned int)(j + 1) )
          {
            v23 = 48 * j;
            v14 = *((_QWORD *)v3 + 18);
            v28[0] = *(_OWORD *)(48 * j + v14);
            v28[1] = *(_OWORD *)(48 * j + v14 + 16);
            if ( !(unsigned int)DafInPropertyList(i, (_DWORD)v9, (unsigned int)v28, v10, 0) )
            {
              v15 = DafDevPropertyCopy(*((_QWORD *)v3 + 18) + v23, &v9[48 * i]);
              if ( v15 < 0 )
                WFDSConMgr::CException::Throw(
                  v15,
                  "WFDSConMgr::CDevQueryHelper::HandleDevQueryCallback",
                  "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\devqueryhelper.cpp",
                  150,
                  L"DafDevPropertyCopy failed (merging old)",
                  v3);
              i = (unsigned int)(i + 1);
            }
          }
          v16 = (char *)*((_QWORD *)v3 + 18);
          *((_QWORD *)v3 + 18) = v9;
          v27 = v16;
          LODWORD(v16) = *((_DWORD *)v3 + 34);
          *((_DWORD *)v3 + 34) = v8;
          v26 = (int)v16;
          *((_DWORD *)v3 + 32) = i;
          if ( (*(unsigned __int8 (__fastcall **)(WFDSConMgr::CDevQueryHelper *))(*(_QWORD *)v3 + 48LL))(v3) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, v3);
            }
            *((_QWORD *)v3 + 44) = 4;
            *((_BYTE *)v3 + 360) = 1;
            v30 = 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, v3);
            }
            v30 = 1;
          }
          std::unique_ptr<_DEVPROPERTY,WFDSConMgr::DafDevPropertyListFreeDeleter>::~unique_ptr<_DEVPROPERTY,WFDSConMgr::DafDevPropertyListFreeDeleter>((__int64)&v26);
          goto LABEL_57;
        }
        goto LABEL_62;
      }
      goto LABEL_57;
    }
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids,
        v3,
        *((_DWORD *)a2 + 2));
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)a2 + 2) == 1 )
    {
      if ( !*((_BYTE *)v3 + 336) )
      {
        if ( v17 == &WPP_GLOBAL_Control || *((_BYTE *)v17 + 25) < 4u || (*((_BYTE *)v17 + 28) & 1) == 0 )
          goto LABEL_63;
        WPP_SF_q(v17[2], 57, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, v3);
LABEL_62:
        v17 = (PVOID *)WPP_GLOBAL_Control;
LABEL_63:
        v30 = 1;
        goto LABEL_94;
      }
      *((_DWORD *)v3 + 89) = -2147023728;
LABEL_57:
      v17 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_94;
    }
    if ( *((_DWORD *)a2 + 2) == 2 )
    {
      *((_DWORD *)v3 + 89) = -2147467260;
      goto LABEL_57;
    }
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = this;
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
    }
    else
    {
      v22 = this;
    }
    *((_DWORD *)v22 + 89) = -2147024882;
    v3 = this;
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  catch ( const std::exception *v25 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v25 + 8LL))(v25);
      v21 = this;
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)&WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids,
        (_DWORD)this,
        v20);
    }
    else
    {
      v21 = this;
    }
    *((_DWORD *)v21 + 89) = -2147418113;
    v3 = this;
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  catch ( const WFDSConMgr::CException *v24 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = v24;
      v19 = this;
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids,
        this,
        *(_DWORD *)v24);
    }
    else
    {
      v19 = this;
      v18 = v24;
    }
    *((_DWORD *)v19 + 89) = *(_DWORD *)v18;
    v3 = this;
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_94:
  if ( v30 )
  {
    if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 25) >= 4u && (*((_BYTE *)v17 + 28) & 1) != 0 )
      WPP_SF_q(v17[2], 64, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, v3);
  }
  else
  {
    WFDSConMgr::CEventWrapper::Set((WFDSConMgr::CDevQueryHelper *)((char *)v3 + 368));
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180027978  mov     rax, rsp
0x18002797b  mov     [rax+10h], rbx
0x18002797f  mov     [rax+8], rcx
0x180027983  push    rdi
0x180027984  push    r12
0x180027986  push    r13
0x180027988  push    r14
0x18002798a  push    r15
0x18002798c  sub     rsp, 80h
0x180027993  mov     r15, rdx
0x180027996  mov     rdi, rcx
0x180027999  mov     [rsp+0A8h+arg_10], 0
0x1800279a1  add     rcx, 0B0h
0x1800279a8  lea     rdx, [rax+20h]
0x1800279ac  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x1800279b1  nop
0x1800279b2  mov     eax, [rdi+160h]
0x1800279b8  add     eax, 0FFFFFFFEh
0x1800279bb  cmp     eax, 1
0x1800279be  jbe     short loc_180027A1C
0x1800279c0  lea     r14, WPP_GLOBAL_Control
0x1800279c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279ce  cmp     rcx, r14
0x1800279d1  jz      short loc_1800279F8
0x1800279d3  cmp     byte ptr [rcx+19h], 4
0x1800279d7  jb      short loc_1800279F8
0x1800279d9  test    byte ptr [rcx+1Ch], 1
0x1800279dd  jz      short loc_1800279F8
0x1800279df  mov     edx, 37h ; '7'
0x1800279e4  mov     r9, rdi
0x1800279e7  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x1800279ee  mov     rcx, [rcx+10h]
0x1800279f2  call    WPP_SF_q
0x1800279f7  nop
0x1800279f8  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x180027a00  test    rcx, rcx
0x180027a03  jz      short loc_180027A17
0x180027a05  call    cs:__imp_LeaveCriticalSection
0x180027a0b  mov     [rsp+0A8h+lpCriticalSection], 0
0x180027a17  jmp     loc_180027E35
0x180027a1c  mov     ecx, [r15]
0x180027a1f  test    ecx, ecx
0x180027a21  jz      loc_180027D10
0x180027a27  sub     ecx, 1
0x180027a2a  jz      short loc_180027A3D
0x180027a2c  cmp     ecx, 1
0x180027a2f  jz      short loc_180027A3D
0x180027a31  lea     r14, WPP_GLOBAL_Control
0x180027a38  jmp     loc_180027D83
0x180027a3d  lea     r14, WPP_GLOBAL_Control
0x180027a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a4b  cmp     rcx, r14
0x180027a4e  jz      short loc_180027A98
0x180027a50  cmp     byte ptr [rcx+19h], 4
0x180027a54  jb      short loc_180027A98
0x180027a56  test    byte ptr [rcx+1Ch], 1
0x180027a5a  jz      short loc_180027A98
0x180027a5c  lea     rax, aUpdated; "updated"
0x180027a63  lea     r8, aAdded; "added"
0x180027a6a  cmp     dword ptr [r15], 1
0x180027a6e  cmovnz  r8, rax
0x180027a72  mov     edx, 3Ah ; ':'
0x180027a77  mov     rax, [r15+10h]
0x180027a7b  mov     [rsp+0A8h+var_80], rax; __int64
0x180027a80  mov     [rsp+0A8h+var_88], r8; __int64
0x180027a85  mov     r9, rdi
0x180027a88  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180027a8f  mov     rcx, [rcx+10h]; LoggerHandle
0x180027a93  call    WPP_SF_qSS
0x180027a98  cmp     byte ptr [rdi+7Dh], 0
0x180027a9c  jz      short loc_180027AD1
0x180027a9e  mov     [rsp+0A8h+arg_10], 1
0x180027aa6  mov     rdx, r15; struct _DEV_QUERY_RESULT_ACTION_DATA *
0x180027aa9  mov     rcx, rdi; this
0x180027aac  call    ?IsUpdateForInterfaceQueryRelevant@CDevQueryHelper@WFDSConMgr@@AEAA_NAEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; WFDSConMgr::CDevQueryHelper::IsUpdateForInterfaceQueryRelevant(_DEV_QUERY_RESULT_ACTION_DATA const &)
0x180027ab1  test    al, al
0x180027ab3  jz      loc_180027DB5
0x180027ab9  mov     rdx, [r15+10h]
0x180027abd  mov     rcx, rdx
0x180027ac0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180027ac5  lea     rcx, [rdi+38h]
0x180027ac9  mov     r8, rax
0x180027acc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180027ad1  cmp     dword ptr [r15], 1
0x180027ad5  jnz     short loc_180027B08
0x180027ad7  mov     dword ptr [rdi+80h], 0
0x180027ae1  lea     rcx, [rdi+88h]
0x180027ae8  mov     rax, [rcx+8]
0x180027aec  mov     qword ptr [rcx+8], 0
0x180027af4  test    rax, rax
0x180027af7  jz      short loc_180027B08
0x180027af9  mov     [rsp+0A8h+var_78], rax
0x180027afe  lea     rdx, [rsp+0A8h+var_78]
0x180027b03  call    DafDevPropertyListFree
0x180027b08  mov     r12d, [r15+18h]
0x180027b0c  add     r12d, [rdi+80h]
0x180027b13  lea     rbx, [r12+r12*2]
0x180027b17  shl     rbx, 4
0x180027b1b  mov     rcx, rbx; unsigned __int64
0x180027b1e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027b23  mov     r13, rax
0x180027b26  mov     [rsp+0A8h+var_60], r12d
0x180027b2b  mov     [rsp+0A8h+var_58], rax
0x180027b30  mov     r8, rbx; Size
0x180027b33  xor     edx, edx; Val
0x180027b35  mov     rcx, rax; void *
0x180027b38  call    memset_0
0x180027b3d  xor     ebx, ebx
0x180027b3f  cmp     ebx, [r15+18h]
0x180027b43  jnb     short loc_180027B8E
0x180027b45  lea     rcx, [rbx+rbx*2]
0x180027b49  shl     rcx, 4
0x180027b4d  lea     rdx, [rcx+r13]
0x180027b51  add     rcx, [r15+20h]
0x180027b55  call    DafDevPropertyCopy
0x180027b5a  test    eax, eax
0x180027b5c  jns     short loc_180027B8A
0x180027b5e  mov     [rsp+0A8h+var_80], rdi; void *
0x180027b63  lea     rcx, aDafdevproperty; "DafDevPropertyCopy failed"
0x180027b6a  mov     [rsp+0A8h+var_88], rcx; unsigned __int16 *
0x180027b6f  mov     r9d, 48Ch; char
0x180027b75  lea     r8, aOnecoreuapNetW_27; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180027b7c  lea     rdx, aWfdsconmgrCdev_18; "WFDSConMgr::CDevQueryHelper::HandleDevQ"...
0x180027b83  mov     ecx, eax; char
0x180027b85  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180027b8a  inc     ebx
0x180027b8c  jmp     short loc_180027B3F
0x180027b8e  xor     r15d, r15d
0x180027b91  cmp     r15d, [rdi+80h]
0x180027b98  jnb     loc_180027C40
0x180027b9e  cmp     ebx, r12d
0x180027ba1  jnb     loc_180027C40
0x180027ba7  lea     rcx, [r15+r15*2]
0x180027bab  shl     rcx, 4
0x180027baf  mov     [rsp+0A8h+var_78], rcx
0x180027bb4  mov     rax, [rdi+90h]
0x180027bbb  movups  xmm0, xmmword ptr [rcx+rax]
0x180027bbf  movaps  [rsp+0A8h+var_48], xmm0
0x180027bc4  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x180027bc9  movaps  [rsp+0A8h+var_38], xmm1
0x180027bce  mov     [rsp+0A8h+var_88], 0
0x180027bd7  lea     r8, [rsp+0A8h+var_48]
0x180027bdc  mov     rdx, r13
0x180027bdf  mov     ecx, ebx
0x180027be1  call    DafInPropertyList
0x180027be6  test    eax, eax
0x180027be8  jnz     short loc_180027C38
0x180027bea  lea     rdx, [rbx+rbx*2]
0x180027bee  shl     rdx, 4
0x180027bf2  add     rdx, r13
0x180027bf5  mov     rcx, [rsp+0A8h+var_78]
0x180027bfa  add     rcx, [rdi+90h]
0x180027c01  call    DafDevPropertyCopy
0x180027c06  test    eax, eax
0x180027c08  jns     short loc_180027C36
0x180027c0a  mov     [rsp+0A8h+var_80], rdi; void *
0x180027c0f  lea     rcx, aDafdevproperty_0; "DafDevPropertyCopy failed (merging old)"
0x180027c16  mov     [rsp+0A8h+var_88], rcx; unsigned __int16 *
0x180027c1b  mov     r9d, 496h; char
0x180027c21  lea     r8, aOnecoreuapNetW_27; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180027c28  lea     rdx, aWfdsconmgrCdev_18; "WFDSConMgr::CDevQueryHelper::HandleDevQ"...
0x180027c2f  mov     ecx, eax; char
0x180027c31  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180027c36  inc     ebx
0x180027c38  inc     r15d
0x180027c3b  jmp     loc_180027B91
0x180027c40  mov     rax, [rdi+90h]
0x180027c47  mov     [rdi+90h], r13
0x180027c4e  mov     [rsp+0A8h+var_58], rax
0x180027c53  mov     eax, [rdi+88h]
0x180027c59  mov     [rdi+88h], r12d
0x180027c60  mov     [rsp+0A8h+var_60], eax
0x180027c64  mov     [rdi+80h], ebx
0x180027c6a  mov     rax, [rdi]
0x180027c6d  mov     rcx, rdi
0x180027c70  mov     rax, [rax+30h]
0x180027c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c79  test    al, al
0x180027c7b  jnz     short loc_180027CC4
0x180027c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c84  cmp     rcx, r14
0x180027c87  jz      short loc_180027CAD
0x180027c89  cmp     byte ptr [rcx+19h], 4
0x180027c8d  jb      short loc_180027CAD
0x180027c8f  test    byte ptr [rcx+1Ch], 1
0x180027c93  jz      short loc_180027CAD
0x180027c95  mov     edx, 3Bh ; ';'
0x180027c9a  mov     r9, rdi
0x180027c9d  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180027ca4  mov     rcx, [rcx+10h]
0x180027ca8  call    WPP_SF_q
0x180027cad  mov     [rsp+0A8h+arg_10], 1
0x180027cb5  lea     rcx, [rsp+0A8h+var_60]
0x180027cba  call    ??1?$unique_ptr@U_DEVPROPERTY@@UDafDevPropertyListFreeDeleter@WFDSConMgr@@@std@@QEAA@XZ; std::unique_ptr<_DEVPROPERTY,WFDSConMgr::DafDevPropertyListFreeDeleter>::~unique_ptr<_DEVPROPERTY,WFDSConMgr::DafDevPropertyListFreeDeleter>(void)
0x180027cbf  jmp     loc_180027D83
0x180027cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ccb  cmp     rcx, r14
0x180027cce  jz      short loc_180027CF4
0x180027cd0  cmp     byte ptr [rcx+19h], 4
0x180027cd4  jb      short loc_180027CF4
0x180027cd6  test    byte ptr [rcx+1Ch], 1
0x180027cda  jz      short loc_180027CF4
0x180027cdc  mov     edx, 3Ch ; '<'
0x180027ce1  mov     r9, rdi
0x180027ce4  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180027ceb  mov     rcx, [rcx+10h]
0x180027cef  call    WPP_SF_q
0x180027cf4  mov     qword ptr [rdi+160h], 4
0x180027cff  mov     byte ptr [rdi+168h], 1
0x180027d06  mov     [rsp+0A8h+arg_10], 0
0x180027d0e  jmp     short loc_180027CB5
0x180027d10  lea     r14, WPP_GLOBAL_Control
0x180027d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d1e  cmp     rcx, r14
0x180027d21  jz      short loc_180027D56
0x180027d23  cmp     byte ptr [rcx+19h], 4
0x180027d27  jb      short loc_180027D56
0x180027d29  test    byte ptr [rcx+1Ch], 1
0x180027d2d  jz      short loc_180027D56
0x180027d2f  mov     edx, 38h ; '8'
0x180027d34  mov     eax, [r15+8]
0x180027d38  mov     dword ptr [rsp+0A8h+var_88], eax
0x180027d3c  mov     r9, rdi
0x180027d3f  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180027d46  mov     rcx, [rcx+10h]
0x180027d4a  call    WPP_SF_qD
0x180027d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d56  mov     edx, [r15+8]
0x180027d5a  sub     edx, 1
0x180027d5d  jz      short loc_180027D70
0x180027d5f  cmp     edx, 1
0x180027d62  jnz     short loc_180027DC4
0x180027d64  mov     dword ptr [rdi+164h], 80004004h
0x180027d6e  jmp     short loc_180027D83
0x180027d70  cmp     byte ptr [rdi+150h], 0
0x180027d77  jz      short loc_180027D8C
0x180027d79  mov     dword ptr [rdi+164h], 80070490h
0x180027d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d8a  jmp     short loc_180027DC4
0x180027d8c  cmp     rcx, r14
0x180027d8f  jz      short loc_180027DBC
0x180027d91  cmp     byte ptr [rcx+19h], 4
0x180027d95  jb      short loc_180027DBC
0x180027d97  test    byte ptr [rcx+1Ch], 1
0x180027d9b  jz      short loc_180027DBC
0x180027d9d  mov     edx, 39h ; '9'
0x180027da2  mov     r9, rdi
0x180027da5  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180027dac  mov     rcx, [rcx+10h]
0x180027db0  call    WPP_SF_q
0x180027db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180027dbc  mov     [rsp+0A8h+arg_10], 1
0x180027dc4  jmp     short loc_180027DE0
0x180027dc6  jmp     short loc_180027DCA
0x180027dc8  jmp     short $+2
0x180027dca  lea     r14, WPP_GLOBAL_Control
0x180027dd1  mov     rdi, [rsp+0A8h+arg_0]
0x180027dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180027de0  cmp     [rsp+0A8h+arg_10], 0
0x180027de8  jnz     short loc_180027DF8
0x180027dea  lea     rcx, [rdi+170h]; this
0x180027df1  call    ?Set@CEventWrapper@WFDSConMgr@@QEAAXXZ; WFDSConMgr::CEventWrapper::Set(void)
0x180027df6  jmp     short loc_180027E22
0x180027df8  cmp     rcx, r14
0x180027dfb  jz      short loc_180027E22
0x180027dfd  cmp     byte ptr [rcx+19h], 4
0x180027e01  jb      short loc_180027E22
0x180027e03  test    byte ptr [rcx+1Ch], 1
0x180027e07  jz      short loc_180027E22
0x180027e09  mov     edx, 40h ; '@'
0x180027e0e  mov     r9, rdi
0x180027e11  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180027e18  mov     rcx, [rcx+10h]
0x180027e1c  call    WPP_SF_q
0x180027e21  nop
0x180027e22  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x180027e2a  test    rcx, rcx
0x180027e2d  jz      short loc_180027E35
0x180027e2f  call    cs:__imp_LeaveCriticalSection
0x180027e35  mov     rbx, [rsp+0A8h+arg_8]
0x180027e3d  add     rsp, 80h
0x180027e44  pop     r15
0x180027e46  pop     r14
0x180027e48  pop     r13
0x180027e4a  pop     r12
0x180027e4c  pop     rdi
0x180027e4d  retn
```
