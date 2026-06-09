# CSsdpCacheEntry::HrUpdateExpireTime(_SSDP_REQUEST const *)

- ea: `0x18000962c`
- end: `0x180009732`
- name: `?HrUpdateExpireTime@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, const struct _SSDP_REQUEST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180023484`

## callees

- `0x180006fd0`
- `0x180008800`
- `0x18000962c`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009696`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009646`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009646`

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
0x18000962c  push    rbx
0x18000962e  push    rsi
0x18000962f  push    rdi
0x180009630  push    r14
0x180009632  sub     rsp, 28h
0x180009636  lea     rsi, [rcx+0D8h]
0x18000963d  mov     rdi, rcx
0x180009640  mov     rcx, rsi; lpCriticalSection
0x180009643  mov     rbx, rdx
0x180009646  call    cs:__imp_EnterCriticalSection
0x18000964d  nop     dword ptr [rax+rax+00h]
0x180009652  mov     rax, [rbx+50h]
0x180009656  lea     r14, WPP_GLOBAL_Control
0x18000965d  mov     rcx, [rax+48h]; char *
0x180009661  test    rcx, rcx
0x180009664  jz      loc_1800096F9
0x18000966a  call    ?GetMaxAgeFromCacheControl@@YAHPEBD@Z; GetMaxAgeFromCacheControl(char const *)
0x18000966f  cmp     eax, 0FFFFFFFFh
0x180009672  jz      loc_18000970C
0x180009678  imul    edx, eax, 3E8h; DueTime
0x18000967e  lea     rcx, [rdi+78h]; Parameter
0x180009682  call    ?HrResetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrResetTimer(ulong)
0x180009687  mov     dword ptr [rdi], 0
0x18000968d  mov     ebx, eax
0x18000968f  test    eax, eax
0x180009691  jnz     short loc_1800096CD
0x180009693  mov     rcx, rsi; lpCriticalSection
0x180009696  call    cs:__imp_LeaveCriticalSection
0x18000969d  nop     dword ptr [rax+rax+00h]
0x1800096a2  mov     eax, ebx
0x1800096a4  add     rsp, 28h
0x1800096a8  pop     r14
0x1800096aa  pop     rdi
0x1800096ab  pop     rsi
0x1800096ac  pop     rbx
0x1800096ad  retn
0x1800096af  test    byte ptr [rcx+1Ch], 1
0x1800096b3  jz      short loc_1800096D4
0x1800096b5  mov     rcx, [rcx+10h]
0x1800096b9  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x1800096c0  mov     edx, 20h ; ' '
0x1800096c5  mov     r9d, ebx
0x1800096c8  call    WPP_SF_d
0x1800096cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096d4  cmp     rcx, r14
0x1800096d7  jz      short loc_180009693
0x1800096d9  test    byte ptr [rcx+1Ch], 1
0x1800096dd  jz      short loc_180009693
0x1800096df  mov     edx, 22h ; '"'
0x1800096e4  mov     rcx, [rcx+10h]
0x1800096e8  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x1800096ef  mov     r9d, ebx
0x1800096f2  call    WPP_SF_d
0x1800096f7  jmp     short loc_180009693
0x1800096f9  mov     ebx, 80070057h
0x1800096fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180009705  cmp     rcx, r14
0x180009708  jz      short loc_180009693
0x18000970a  jmp     short loc_1800096AF
0x18000970c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009713  mov     ebx, 80070057h
0x180009718  cmp     rcx, r14
0x18000971b  jz      loc_180009693
0x180009721  test    byte ptr [rcx+1Ch], 1
0x180009725  jz      loc_180009693
0x18000972b  mov     edx, 21h ; '!'
0x180009730  jmp     short loc_1800096E4
```
