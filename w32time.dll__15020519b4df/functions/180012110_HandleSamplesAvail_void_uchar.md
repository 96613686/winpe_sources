# HandleSamplesAvail(void *,uchar)

- ea: `0x180012110`
- end: `0x18001239d`
- name: `?HandleSamplesAvail@@YAXPEAXE@Z`
- size: `653`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x18000e620`
- `0x18000f400`
- `0x180011120`
- `0x180012110`
- `0x180018138`
- `0x180018dfc`
- `0x18001d9a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001213b`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180012237`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001213b`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180012237`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001237d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001237d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012156`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122c8`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180012213`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180012213`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800121df`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800121df`

## string_xrefs

- `0x180012314`: `W32TmServiceMain: resync req,`
- `0x180012347`: ` irreg already pending.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HandleSamplesAvail(void *a1)
{
  unsigned __int64 v1; // rax
  char v2; // [rsp+31h] [rbp-47h]
  __int64 v3; // [rsp+90h] [rbp+18h]

  v2 = 0;
  if ( (unsigned __int8)FileLogAllowEntry(64) )
    FileLogAdd(L"W32TmServiceMain: resync req,");
  v3 = _set_se_translator(SeTransFunc);
  EnterCriticalSection(&CriticalSection);
  if ( (int)UpdateTimerQueue2() >= 0 )
  {
    if ( byte_1800A46A0 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(64) )
        FileLogAppend(L" user requested, get samples as soon as possible.\n");
      qword_1800A4320 = 1;
    }
    else if ( qword_1800A4320 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(64) )
        FileLogAppend(L" irreg already pending.\n");
    }
    else
    {
      qword_1800A4320 = 160000000;
      if ( (unsigned __int64)qword_1800A4328 > 0x9896800 )
      {
        qword_1800A4320 = 1;
        v1 = 1;
      }
      else
      {
        v1 = 160000001 - qword_1800A4328;
        qword_1800A4320 = 160000001 - qword_1800A4328;
      }
      if ( v1 > qword_1800A4310 || qword_1800A4310 - v1 <= 0x9896800 )
      {
        qword_1800A4320 = 0;
        if ( (unsigned __int8)FileLogAllowEntry(64) )
          FileLogAppend(L" reg too soon.\n");
      }
      else if ( (unsigned __int8)FileLogAllowEntry(64) )
      {
        FileLogAppend(L" irreg now pending.\n");
      }
    }
    if ( (int)UpdateTimerQueue1() >= 0 && (int)AllowShutdown(0) >= 0 )
    {
      v2 = 1;
      if ( qword_1800A3798 )
      {
        UnregisterWaitEx(qword_1800A3798, 0);
        qword_1800A3798 = 0;
      }
      qword_1800A3798 = (HANDLE)RegisterWaitForSingleObjectEx(qword_1800A3730, HandleSamplesAvail, 0, 0xFFFFFFFFLL, 8);
      if ( qword_1800A3798 )
        _set_se_translator(v3);
      else
        GetLastError();
    }
  }
  LeaveCriticalSection(&CriticalSection);
  if ( v2 )
    AllowShutdown(1);
}

```

## disassembly

```asm
0x180012110  push    rbx
0x180012112  sub     rsp, 70h
0x180012116  mov     [rsp+78h+var_47], 0
0x18001211b  mov     [rsp+78h+var_48], 0
0x180012120  mov     ebx, 40h ; '@'
0x180012125  mov     ecx, ebx
0x180012127  call    FileLogAllowEntry
0x18001212c  test    al, al
0x18001212e  jnz     loc_180012314
0x180012134  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18001213b  call    cs:__imp__set_se_translator
0x180012142  nop     dword ptr [rax+rax+00h]
0x180012147  mov     [rsp+78h+arg_10], rax
0x18001214f  lea     rcx, CriticalSection; lpCriticalSection
0x180012156  call    cs:__imp_EnterCriticalSection
0x18001215d  nop     dword ptr [rax+rax+00h]
0x180012162  mov     [rsp+78h+var_44], 0
0x18001216a  mov     [rsp+78h+var_48], 1
0x18001216f  call    ?UpdateTimerQueue2@@YAJXZ; UpdateTimerQueue2(void)
0x180012174  mov     [rsp+78h+var_44], eax
0x180012178  test    eax, eax
0x18001217a  js      loc_180012325
0x180012180  mov     al, cs:byte_1800A46A0
0x180012186  test    al, al
0x180012188  jz      loc_180012260
0x18001218e  mov     ecx, ebx
0x180012190  call    FileLogAllowEntry
0x180012195  test    al, al
0x180012197  jnz     loc_180012327
0x18001219d  mov     cs:qword_1800A4320, 1
0x1800121a8  call    ?UpdateTimerQueue1@@YAJXZ; UpdateTimerQueue1(void)
0x1800121ad  mov     [rsp+78h+var_44], eax
0x1800121b1  test    eax, eax
0x1800121b3  js      loc_1800122C3
0x1800121b9  xor     ecx, ecx; int
0x1800121bb  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x1800121c0  mov     [rsp+78h+var_44], eax
0x1800121c4  test    eax, eax
0x1800121c6  js      loc_180012365
0x1800121cc  mov     [rsp+78h+var_47], 1
0x1800121d1  mov     rcx, cs:qword_1800A3798; WaitHandle
0x1800121d8  test    rcx, rcx
0x1800121db  jz      short loc_1800121F6
0x1800121dd  xor     edx, edx; CompletionEvent
0x1800121df  call    cs:__imp_UnregisterWaitEx
0x1800121e6  nop     dword ptr [rax+rax+00h]
0x1800121eb  mov     cs:qword_1800A3798, 0
0x1800121f6  mov     [rsp+78h+var_58], 8
0x1800121fe  or      r9d, 0FFFFFFFFh
0x180012202  xor     r8d, r8d
0x180012205  lea     rdx, ?HandleSamplesAvail@@YAXPEAXE@Z; HandleSamplesAvail(void *,uchar)
0x18001220c  mov     rcx, cs:qword_1800A3730
0x180012213  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18001221a  nop     dword ptr [rax+rax+00h]
0x18001221f  mov     cs:qword_1800A3798, rax
0x180012226  test    rax, rax
0x180012229  jz      loc_1800122C8
0x18001222f  mov     rcx, [rsp+78h+arg_10]
0x180012237  call    cs:__imp__set_se_translator
0x18001223e  nop     dword ptr [rax+rax+00h]
0x180012243  cmp     [rsp+78h+var_48], 0
0x180012248  jnz     loc_180012376
0x18001224e  cmp     [rsp+78h+var_47], 0
0x180012253  jnz     loc_18001238E
0x180012259  add     rsp, 70h
0x18001225d  pop     rbx
0x18001225e  retn
0x180012260  cmp     cs:qword_1800A4320, 0
0x180012268  jnz     loc_180012338
0x18001226e  mov     edx, 9896800h
0x180012273  mov     cs:qword_1800A4320, rdx
0x18001227a  mov     rcx, cs:qword_1800A4328
0x180012281  cmp     rcx, rdx
0x180012284  ja      loc_180012350
0x18001228a  lea     eax, [rdx+1]
0x18001228d  sub     rax, rcx
0x180012290  mov     cs:qword_1800A4320, rax
0x180012297  mov     rcx, cs:qword_1800A4310
0x18001229e  cmp     rax, rcx
0x1800122a1  ja      short loc_1800122E9
0x1800122a3  sub     rcx, rax
0x1800122a6  cmp     rcx, rdx
0x1800122a9  jbe     short loc_1800122E9
0x1800122ab  mov     ecx, ebx
0x1800122ad  call    FileLogAllowEntry
0x1800122b2  test    al, al
0x1800122b4  jz      loc_1800121A8
0x1800122ba  lea     rcx, aIrregNowPendin; " irreg now pending.\n"
0x1800122c1  jmp     short loc_18001230A
0x1800122c3  jmp     loc_180012376
0x1800122c8  call    cs:__imp_GetLastError
0x1800122cf  nop     dword ptr [rax+rax+00h]
0x1800122d4  test    eax, eax
0x1800122d6  jle     short loc_1800122E0
0x1800122d8  movzx   eax, ax
0x1800122db  or      eax, 80070000h
0x1800122e0  mov     [rsp+78h+var_44], eax
0x1800122e4  jmp     loc_180012376
0x1800122e9  mov     cs:qword_1800A4320, 0
0x1800122f4  mov     ecx, ebx
0x1800122f6  call    FileLogAllowEntry
0x1800122fb  test    al, al
0x1800122fd  jz      loc_1800121A8
0x180012303  lea     rcx, aRegTooSoon; " reg too soon.\n"
0x18001230a  call    FileLogAppend
0x18001230f  jmp     loc_1800121A8
0x180012314  lea     rcx, aW32tmservicema_13; "W32TmServiceMain: resync req,"
0x18001231b  call    FileLogAdd
0x180012320  jmp     loc_180012134
0x180012325  jmp     short loc_180012376
0x180012327  lea     rcx, aUserRequestedG; " user requested, get samples as soon as"...
0x18001232e  call    FileLogAppend
0x180012333  jmp     loc_18001219D
0x180012338  mov     ecx, ebx
0x18001233a  call    FileLogAllowEntry
0x18001233f  test    al, al
0x180012341  jz      loc_1800121A8
0x180012347  lea     rcx, aIrregAlreadyPe; " irreg already pending.\n"
0x18001234e  jmp     short loc_18001230A
0x180012350  mov     cs:qword_1800A4320, 1
0x18001235b  mov     eax, 1
0x180012360  jmp     loc_180012297
0x180012365  jmp     short loc_180012376
0x180012367  jmp     loc_18001222F
0x18001236c  jmp     loc_18001222F
0x180012371  jmp     loc_18001222F
0x180012376  lea     rcx, CriticalSection; lpCriticalSection
0x18001237d  call    cs:__imp_LeaveCriticalSection
0x180012384  nop     dword ptr [rax+rax+00h]
0x180012389  jmp     loc_18001224E
0x18001238e  mov     ecx, 1; int
0x180012393  add     rsp, 70h
0x180012397  pop     rbx
0x180012398  jmp     ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
```
