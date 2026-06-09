# CSsdpCacheEntry::HrUpdateExpireTime(_SSDP_REQUEST const *)

- ea: `0x180007bec`
- end: `0x180007ce5`
- name: `?HrUpdateExpireTime@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, const struct _SSDP_REQUEST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180021c90`

## callees

- `0x180005c90`
- `0x180007360`
- `0x180007bec`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c06`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::HrUpdateExpireTime(CSsdpCacheEntry *this, const struct _SSDP_REQUEST *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  const char *v5; // rcx
  int MaxAgeFromCacheControl; // eax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  LPCSTR v10; // rcx
  __int64 v11; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v5 = *(const char **)(*((_QWORD *)a2 + 10) + 72LL);
  if ( !v5 )
  {
    v8 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
      goto LABEL_4;
    if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
    {
LABEL_8:
      if ( v10 != (LPCSTR)&WPP_GLOBAL_Control && (v10[28] & 1) != 0 )
      {
        v11 = 34;
LABEL_11:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v8);
        goto LABEL_4;
      }
      goto LABEL_4;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147942487LL);
LABEL_7:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  MaxAgeFromCacheControl = GetMaxAgeFromCacheControl(v5);
  if ( MaxAgeFromCacheControl != -1 )
  {
    v7 = CTimerBase::HrResetTimer((char *)this + 120, 1000 * MaxAgeFromCacheControl);
    *(_DWORD *)this = 0;
    v8 = v7;
    if ( !v7 )
      goto LABEL_4;
    goto LABEL_7;
  }
  v10 = WPP_GLOBAL_Control;
  v8 = -2147024809;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    v11 = 33;
    goto LABEL_11;
  }
LABEL_4:
  LeaveCriticalSection(v2);
  return v8;
}

```

## disassembly

```asm
0x180007bec  push    rbx
0x180007bee  push    rsi
0x180007bef  push    rdi
0x180007bf0  push    r14
0x180007bf2  sub     rsp, 28h
0x180007bf6  lea     rsi, [rcx+0D8h]
0x180007bfd  mov     rdi, rcx
0x180007c00  mov     rcx, rsi; lpCriticalSection
0x180007c03  mov     rbx, rdx
0x180007c06  call    cs:__imp_EnterCriticalSection
0x180007c0c  mov     rax, [rbx+50h]
0x180007c10  lea     r14, WPP_GLOBAL_Control
0x180007c17  mov     rcx, [rax+48h]; char *
0x180007c1b  test    rcx, rcx
0x180007c1e  jz      loc_180007CAC
0x180007c24  call    ?GetMaxAgeFromCacheControl@@YAHPEBD@Z; GetMaxAgeFromCacheControl(char const *)
0x180007c29  cmp     eax, 0FFFFFFFFh
0x180007c2c  jz      loc_180007CBF
0x180007c32  imul    edx, eax, 3E8h; DueTime
0x180007c38  lea     rcx, [rdi+78h]; Parameter
0x180007c3c  call    ?HrResetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrResetTimer(ulong)
0x180007c41  mov     dword ptr [rdi], 0
0x180007c47  mov     ebx, eax
0x180007c49  test    eax, eax
0x180007c4b  jnz     short loc_180007C80
0x180007c4d  mov     rcx, rsi; lpCriticalSection
0x180007c50  call    cs:__imp_LeaveCriticalSection
0x180007c56  mov     eax, ebx
0x180007c58  add     rsp, 28h
0x180007c5c  pop     r14
0x180007c5e  pop     rdi
0x180007c5f  pop     rsi
0x180007c60  pop     rbx
0x180007c61  retn
0x180007c62  test    byte ptr [rcx+1Ch], 1
0x180007c66  jz      short loc_180007C87
0x180007c68  mov     rcx, [rcx+10h]
0x180007c6c  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180007c73  mov     edx, 20h ; ' '
0x180007c78  mov     r9d, ebx
0x180007c7b  call    WPP_SF_d
0x180007c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c87  cmp     rcx, r14
0x180007c8a  jz      short loc_180007C4D
0x180007c8c  test    byte ptr [rcx+1Ch], 1
0x180007c90  jz      short loc_180007C4D
0x180007c92  mov     edx, 22h ; '"'
0x180007c97  mov     rcx, [rcx+10h]
0x180007c9b  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180007ca2  mov     r9d, ebx
0x180007ca5  call    WPP_SF_d
0x180007caa  jmp     short loc_180007C4D
0x180007cac  mov     ebx, 80070057h
0x180007cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cb8  cmp     rcx, r14
0x180007cbb  jz      short loc_180007C4D
0x180007cbd  jmp     short loc_180007C62
0x180007cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cc6  mov     ebx, 80070057h
0x180007ccb  cmp     rcx, r14
0x180007cce  jz      loc_180007C4D
0x180007cd4  test    byte ptr [rcx+1Ch], 1
0x180007cd8  jz      loc_180007C4D
0x180007cde  mov     edx, 21h ; '!'
0x180007ce3  jmp     short loc_180007C97
```
