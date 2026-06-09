# SeqGetCurrentExecutionGroup

- ea: `0x180003804`
- end: `0x180003950`
- name: `SeqGetCurrentExecutionGroup`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000d190`

## callees

- `0x180002250`
- `0x180003804`
- `0x180005da4`
- `0x18000720c`
- `0x180008a6c`
- `0x18000bca4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000386c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000386c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003926`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003926`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027ae8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003854`

## string_xrefs

- `0x18000387a`: `Attempt to use SeqGetCurrentExecutionGroup from another thread`

## pseudocode

```c
__int64 __fastcall SeqGetCurrentExecutionGroup(__int64 a1, wchar_t *a2, _DWORD *a3)
{
  BOOL v6; // r14d
  __int64 result; // rax
  int v8; // ebx
  DWORD LastError; // ebx
  int v10; // eax
  __int64 NonDeletedItem; // rax
  __int64 v12; // r11
  __int64 v13; // rax
  LPCWSTR lpModuleName; // [rsp+88h] [rbp+0h]

  v6 = 0;
  result = IsWorkQueueAccessible(L"SeqGetCurrentExecutionGroup");
  if ( (_DWORD)result )
  {
    pLock(a1);
    v8 = *(_DWORD *)(a1 + 176);
    if ( GetCurrentThreadId() == v8 )
    {
      NonDeletedItem = privateGetNonDeletedItem(**(_QWORD **)(a1 + 56), 1);
      v12 = NonDeletedItem;
      if ( NonDeletedItem )
      {
        if ( a2 )
          v6 = StringCchCopyW(a2, (unsigned int)*a3, *(STRSAFE_LPCWSTR *)(NonDeletedItem + 48)) >= 0;
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)(*(_QWORD *)(v12 + 48) + 2 * v13) );
        *a3 = v13 + 1;
      }
      else
      {
        *a3 = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      v10 = (unsigned int)ConstructPartialMsgW(
                            0x300007Au,
                            "Attempt to use SeqGetCurrentExecutionGroup from another thread");
      WdsSetupLogMessageW(
        v10,
        589824,
        (int)L"D",
        0,
        1644,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        (__int64)L"SeqGetCurrentExecutionGroup",
        lpModuleName,
        LastError,
        0,
        0);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180003804  mov     [rsp+arg_8], rbx
0x180003809  mov     [rsp+arg_10], rsi
0x18000380e  mov     [rsp+arg_0], rcx
0x180003813  push    rdi
0x180003814  push    r12
0x180003816  push    r13
0x180003818  push    r14
0x18000381a  push    r15
0x18000381c  sub     rsp, 60h
0x180003820  mov     rdi, r8
0x180003823  mov     r15, rdx
0x180003826  mov     rsi, rcx
0x180003829  xor     r12d, r12d
0x18000382c  mov     r14d, r12d
0x18000382f  lea     r13, aSeqgetcurrente; "SeqGetCurrentExecutionGroup"
0x180003836  mov     rcx, r13
0x180003839  call    IsWorkQueueAccessible
0x18000383e  test    eax, eax
0x180003840  jz      loc_180003935
0x180003846  mov     rcx, rsi
0x180003849  call    pLock
0x18000384e  mov     ebx, [rsi+0B0h]
0x180003854  call    cs:__imp_GetCurrentThreadId
0x18000385b  nop     dword ptr [rax+rax+00h]
0x180003860  cmp     eax, ebx
0x180003862  jz      short loc_1800038D0
0x180003864  mov     rdi, [rsp+88h]
0x18000386c  call    cs:__imp_GetLastError
0x180003873  nop     dword ptr [rax+rax+00h]
0x180003878  mov     ebx, eax
0x18000387a  lea     rdx, aAttemptToUseSe_0; "Attempt to use SeqGetCurrentExecutionGr"...
0x180003881  mov     ecx, 300007Ah; unsigned int
0x180003886  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000388b  mov     rcx, rax; int
0x18000388e  mov     [rsp+88h+var_38], r12d; int
0x180003893  mov     [rsp+88h+var_40], r12; __int64
0x180003898  mov     [rsp+88h+var_48], ebx; int
0x18000389c  mov     [rsp+88h+lpModuleName], rdi; lpModuleName
0x1800038a1  mov     [rsp+88h+var_58], r13; __int64
0x1800038a6  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800038ad  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x1800038b2  mov     [rsp+88h+var_68], 66Ch; int
0x1800038ba  xor     r9d, r9d; int
0x1800038bd  lea     r8, aD_1; "D"
0x1800038c4  mov     edx, 90000h; int
0x1800038c9  call    WdsSetupLogMessageW
0x1800038ce  jmp     short loc_18000391F
0x1800038d0  mov     rcx, [rsi+38h]
0x1800038d4  mov     ebx, 1
0x1800038d9  mov     edx, ebx
0x1800038db  mov     rcx, [rcx]
0x1800038de  call    privateGetNonDeletedItem
0x1800038e3  mov     r11, rax
0x1800038e6  test    rax, rax
0x1800038e9  jz      short loc_18000391C
0x1800038eb  test    r15, r15
0x1800038ee  jz      short loc_180003904
0x1800038f0  mov     edx, [rdi]; cchDest
0x1800038f2  mov     r8, [rax+30h]; pszSrc
0x1800038f6  mov     rcx, r15; pszDest
0x1800038f9  call    StringCchCopyW
0x1800038fe  test    eax, eax
0x180003900  cmovns  r14d, ebx
0x180003904  mov     rcx, [r11+30h]
0x180003908  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000390c  inc     rax
0x18000390f  cmp     [rcx+rax*2], r12w
0x180003914  jnz     short loc_18000390C
0x180003916  inc     eax
0x180003918  mov     [rdi], eax
0x18000391a  jmp     short loc_18000391F
0x18000391c  mov     [rdi], r12d
0x18000391f  lea     rcx, [rsi+0B8h]; lpCriticalSection
0x180003926  call    cs:__imp_LeaveCriticalSection
0x18000392d  nop     dword ptr [rax+rax+00h]
0x180003932  mov     eax, r14d
0x180003935  lea     r11, [rsp+88h+var_28]
0x18000393a  mov     rbx, [r11+38h]
0x18000393e  mov     rsi, [r11+40h]
0x180003942  mov     rsp, r11
0x180003945  pop     r15
0x180003947  pop     r14
0x180003949  pop     r13
0x18000394b  pop     r12
0x18000394d  pop     rdi
0x18000394e  retn
0x180027acc  push    rbp
0x180027ace  sub     rsp, 60h
0x180027ad2  mov     rbp, rdx
0x180027ad5  mov     rcx, [rbp+90h]
0x180027adc  add     rcx, 0B8h
0x180027ae3  add     rsp, 60h
0x180027ae7  pop     rbp
0x180027ae8  jmp     cs:__imp_LeaveCriticalSection
```
