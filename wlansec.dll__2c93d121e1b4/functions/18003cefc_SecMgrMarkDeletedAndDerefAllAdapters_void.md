# SecMgrMarkDeletedAndDerefAllAdapters(void)

- ea: `0x18003cefc`
- end: `0x18003d184`
- name: `?SecMgrMarkDeletedAndDerefAllAdapters@@YAXXZ`
- size: `648`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180050648`

## callees

- `0x180003c78`
- `0x180004518`
- `0x18000892c`
- `0x180008998`
- `0x18003cefc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003d133`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003d133`
- `MobileNetworking!ReleaseWriteLock` at `0x18003d055`
- `MobileNetworking!ReleaseWriteLock` at `0x18003d0f9`
- `MobileNetworking!ReleaseWriteLock` at `0x18003d055`
- `MobileNetworking!ReleaseWriteLock` at `0x18003d0f9`
- `MobileNetworking!AcquireWriteLock` at `0x18003cf61`
- `MobileNetworking!AcquireWriteLock` at `0x18003d0c6`
- `MobileNetworking!AcquireWriteLock` at `0x18003cf61`
- `MobileNetworking!AcquireWriteLock` at `0x18003d0c6`

## string_xrefs

- `0x18003cf4c`: `SecMgrMarkDeletedAndDerefAllAdapters`
- `0x18003d040`: `SecMgrMarkDeletedAndDerefAllAdapters`
- `0x18003d0b1`: `SecMgrMarkDeletedAndDerefAllAdapters`
- `0x18003d0d4`: `SecMgrMarkDeletedAndDerefAllAdapters`

## pseudocode

```c
void SecMgrMarkDeletedAndDerefAllAdapters(void)
{
  __int64 v0; // rdi
  int v1; // esi
  __int64 v2; // rax
  __int64 *v3; // rax
  unsigned int v4; // eax
  BOOL v5; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  do
  {
    AcquireWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrMarkDeletedAndDerefAllAdapters", 628);
    v0 = qword_1800AF028;
    if ( (__int64 *)qword_1800AF028 == &qword_1800AF028 )
    {
      v0 = 0;
      v1 = 1;
    }
    else
    {
      if ( *(__int64 **)(qword_1800AF028 + 8) != &qword_1800AF028
        || (v2 = *(_QWORD *)qword_1800AF028, *(_QWORD *)(*(_QWORD *)qword_1800AF028 + 8LL) != qword_1800AF028)
        || (qword_1800AF028 = *(_QWORD *)qword_1800AF028,
            *(_QWORD *)(v2 + 8) = &qword_1800AF028,
            v3 = (__int64 *)qword_1800AF040,
            *(__int64 **)qword_1800AF040 != &qword_1800AF038) )
      {
        __fastfail(3u);
      }
      *(_QWORD *)v0 = &qword_1800AF038;
      v1 = 0;
      *(_QWORD *)(v0 + 8) = v3;
      *v3 = v0;
      qword_1800AF040 = v0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
        WPP_SF_qDDDDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          42,
          *(unsigned __int8 *)(v0 + 2364),
          v0,
          *(unsigned __int8 *)(v0 + 2360),
          *(unsigned __int8 *)(v0 + 2361),
          *(unsigned __int8 *)(v0 + 2362),
          *(unsigned __int8 *)(v0 + 2363),
          *(unsigned __int8 *)(v0 + 2364),
          *(unsigned __int8 *)(v0 + 2365));
    }
    ReleaseWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrMarkDeletedAndDerefAllAdapters", 650);
    if ( v0 )
    {
      v4 = SecMgrMarkDeletedAndDerefAdapter((struct MSMSEC_INTF_CONTEXT *)v0);
      if ( v4 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 43, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v4);
      }
    }
  }
  while ( !v1 );
  while ( 1 )
  {
    AcquireWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrMarkDeletedAndDerefAllAdapters", 662);
    v5 = qword_1800AF038 == (_QWORD)&qword_1800AF038;
    ReleaseWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrMarkDeletedAndDerefAllAdapters", 666);
    if ( v5 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 44, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    Sleep(0x64u);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 45, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, 0);
}

```

## disassembly

```asm
0x18003cefc  push    rbx
0x18003cefe  push    rbp
0x18003ceff  push    rsi
0x18003cf00  push    rdi
0x18003cf01  push    r15
0x18003cf03  sub     rsp, 50h
0x18003cf07  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf0e  lea     rbp, WPP_GLOBAL_Control
0x18003cf15  cmp     rcx, rbp
0x18003cf18  jz      short loc_18003CF38
0x18003cf1a  test    dword ptr [rcx+44h], 100h
0x18003cf21  jz      short loc_18003CF38
0x18003cf23  mov     rcx, [rcx+38h]
0x18003cf27  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18003cf2e  mov     edx, 29h ; ')'
0x18003cf33  call    WPP_SF_
0x18003cf38  lea     r15, qword_1800AF028
0x18003cf3f  lea     rbx, qword_1800AF038
0x18003cf46  mov     r9d, 274h
0x18003cf4c  lea     r8, aSecmgrmarkdele_1; "SecMgrMarkDeletedAndDerefAllAdapters"
0x18003cf53  lea     rdx, qword_1800AEFC0
0x18003cf5a  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x18003cf61  call    cs:__imp_AcquireWriteLock
0x18003cf68  nop     dword ptr [rax+rax+00h]
0x18003cf6d  mov     rdi, cs:qword_1800AF028
0x18003cf74  cmp     rdi, r15
0x18003cf77  jnz     short loc_18003CF83
0x18003cf79  xor     edi, edi
0x18003cf7b  lea     esi, [rdi+1]
0x18003cf7e  jmp     loc_18003D03A
0x18003cf83  cmp     [rdi+8], r15
0x18003cf87  jnz     loc_18003D17D
0x18003cf8d  mov     rax, [rdi]
0x18003cf90  cmp     [rax+8], rdi
0x18003cf94  jnz     loc_18003D17D
0x18003cf9a  mov     cs:qword_1800AF028, rax
0x18003cfa1  mov     [rax+8], r15
0x18003cfa5  mov     rax, cs:qword_1800AF040
0x18003cfac  cmp     [rax], rbx
0x18003cfaf  jnz     loc_18003D17D
0x18003cfb5  mov     [rdi], rbx
0x18003cfb8  xor     esi, esi
0x18003cfba  mov     [rdi+8], rax
0x18003cfbe  mov     [rax], rdi
0x18003cfc1  mov     cs:qword_1800AF040, rdi
0x18003cfc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfcf  cmp     rcx, rbp
0x18003cfd2  jz      short loc_18003D03A
0x18003cfd4  test    byte ptr [rcx+44h], 2
0x18003cfd8  jz      short loc_18003D03A
0x18003cfda  movzx   r9d, byte ptr [rdi+93Bh]
0x18003cfe2  lea     edx, [rsi+2Ah]
0x18003cfe5  movzx   eax, byte ptr [rdi+93Dh]
0x18003cfec  movzx   r8d, byte ptr [rdi+93Ch]
0x18003cff4  movzx   r10d, byte ptr [rdi+93Ah]
0x18003cffc  movzx   r11d, byte ptr [rdi+939h]
0x18003d004  movzx   ebx, byte ptr [rdi+938h]
0x18003d00b  mov     rcx, [rcx+38h]
0x18003d00f  mov     [rsp+78h+var_30], eax
0x18003d013  mov     [rsp+78h+var_38], r8d
0x18003d018  mov     [rsp+78h+var_40], r9d
0x18003d01d  mov     r9, rdi
0x18003d020  mov     [rsp+78h+var_48], r10d
0x18003d025  mov     [rsp+78h+var_50], r11d
0x18003d02a  mov     [rsp+78h+var_58], ebx
0x18003d02e  call    WPP_SF_qDDDDDD
0x18003d033  lea     rbx, qword_1800AF038
0x18003d03a  mov     r9d, 28Ah
0x18003d040  lea     r8, aSecmgrmarkdele_1; "SecMgrMarkDeletedAndDerefAllAdapters"
0x18003d047  lea     rdx, qword_1800AEFC0
0x18003d04e  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x18003d055  call    cs:__imp_ReleaseWriteLock
0x18003d05c  nop     dword ptr [rax+rax+00h]
0x18003d061  test    rdi, rdi
0x18003d064  jz      short loc_18003D09C
0x18003d066  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18003d069  call    ?SecMgrMarkDeletedAndDerefAdapter@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrMarkDeletedAndDerefAdapter(MSMSEC_INTF_CONTEXT *)
0x18003d06e  test    eax, eax
0x18003d070  jz      short loc_18003D09C
0x18003d072  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d079  cmp     rcx, rbp
0x18003d07c  jz      short loc_18003D09C
0x18003d07e  test    byte ptr [rcx+44h], 1
0x18003d082  jz      short loc_18003D09C
0x18003d084  mov     rcx, [rcx+38h]
0x18003d088  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18003d08f  mov     edx, 2Bh ; '+'
0x18003d094  mov     r9d, eax
0x18003d097  call    WPP_SF_d
0x18003d09c  test    esi, esi
0x18003d09e  jz      loc_18003CF46
0x18003d0a4  lea     rdi, qword_1800AF038
0x18003d0ab  mov     r9d, 296h
0x18003d0b1  lea     r8, aSecmgrmarkdele_1; "SecMgrMarkDeletedAndDerefAllAdapters"
0x18003d0b8  lea     rdx, qword_1800AEFC0
0x18003d0bf  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x18003d0c6  call    cs:__imp_AcquireWriteLock
0x18003d0cd  nop     dword ptr [rax+rax+00h]
0x18003d0d2  xor     ebx, ebx
0x18003d0d4  lea     r8, aSecmgrmarkdele_1; "SecMgrMarkDeletedAndDerefAllAdapters"
0x18003d0db  cmp     cs:qword_1800AF038, rdi
0x18003d0e2  lea     rdx, qword_1800AEFC0
0x18003d0e9  mov     r9d, 29Ah
0x18003d0ef  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x18003d0f6  setz    bl
0x18003d0f9  call    cs:__imp_ReleaseWriteLock
0x18003d100  nop     dword ptr [rax+rax+00h]
0x18003d105  test    ebx, ebx
0x18003d107  jnz     short loc_18003D144
0x18003d109  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d110  cmp     rcx, rbp
0x18003d113  jz      short loc_18003D12E
0x18003d115  test    byte ptr [rcx+44h], 2
0x18003d119  jz      short loc_18003D12E
0x18003d11b  mov     rcx, [rcx+38h]
0x18003d11f  lea     edx, [rbx+2Ch]
0x18003d122  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18003d129  call    WPP_SF_
0x18003d12e  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003d133  call    cs:__imp_Sleep
0x18003d13a  nop     dword ptr [rax+rax+00h]
0x18003d13f  jmp     loc_18003D0AB
0x18003d144  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d14b  cmp     rcx, rbp
0x18003d14e  jz      short loc_18003D171
0x18003d150  test    dword ptr [rcx+44h], 100h
0x18003d157  jz      short loc_18003D171
0x18003d159  mov     rcx, [rcx+38h]
0x18003d15d  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18003d164  mov     edx, 2Dh ; '-'
0x18003d169  xor     r9d, r9d
0x18003d16c  call    WPP_SF_d
0x18003d171  add     rsp, 50h
0x18003d175  pop     r15
0x18003d177  pop     rdi
0x18003d178  pop     rsi
0x18003d179  pop     rbp
0x18003d17a  pop     rbx
0x18003d17b  retn
0x18003d17d  mov     ecx, 3
0x18003d182  int     29h; Win8: RtlFailFast(ecx)
```
