# BaseHttpListener::SpawnQueueWorkerThread(char const *,int)

- ea: `0x18001ac40`
- end: `0x18001aed9`
- name: `?SpawnQueueWorkerThread@BaseHttpListener@@IEAAJPEBDH@Z`
- size: `665`
- prototype: `__int64 __fastcall(BaseHttpListener *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001a5ac`
- `0x18001ab80`

## callees

- `0x18001ac40`
- `0x18001aee0`
- `0x180021c04`
- `0x1800242a4`
- `0x1800255a8`
- `0x180028000`
- `0x18002f078`
- `0x1800318f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ae7e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ae87`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ae7e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ae87`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ad51`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ad51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aeba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aeba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae48`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001ae28`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001ae28`

## pseudocode

```c
__int64 __fastcall BaseHttpListener::SpawnQueueWorkerThread(BaseHttpListener *this, const char *a2, int a3)
{
  __int64 v6; // rcx
  __int64 v7; // rbx
  LPCSTR v8; // rdi
  unsigned int v9; // ebx
  void *v10; // rax
  void **v11; // rsi
  DWORD LastError; // eax
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  v6 = *((_QWORD *)this + 21);
  v14 = 0;
  if ( (unsigned int)LKRhash::CLKRHashTable::FindKey(v6, a2, &v14) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    v9 = -2147467260;
    goto LABEL_40;
  }
  v7 = v14;
  if ( a3 )
  {
    *(_DWORD *)(v14 + 32) = 1;
  }
  else if ( !*(_DWORD *)(v14 + 32) )
  {
    goto LABEL_18;
  }
  if ( *(_DWORD *)(v7 + 36) )
  {
LABEL_18:
    v9 = 0;
    goto LABEL_40;
  }
  if ( *(_DWORD *)(v7 + 40) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_13;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      *(unsigned int *)(v7 + 40));
  }
  v8 = WPP_GLOBAL_Control;
LABEL_13:
  if ( **(_DWORD **)(v7 + 24) == *(_DWORD *)(*(_QWORD *)(v7 + 24) + 4LL) )
  {
    if ( v8 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x100) != 0 )
      WPP_SF_(*((_QWORD *)v8 + 2), 120, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    goto LABEL_18;
  }
  v10 = malloc(0x10u);
  v11 = (void **)v10;
  if ( !v10 )
  {
    v9 = -2147024882;
    if ( v8 != (LPCSTR)&WPP_GLOBAL_Control && (v8[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)v8 + 2), 122, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    goto LABEL_40;
  }
  *(_QWORD *)v10 = this;
  DupStr((char **)v10 + 1, a2);
  if ( !v11[1] )
  {
    v9 = -2147024882;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
LABEL_35:
    free(v11[1]);
    free(v11);
    goto LABEL_40;
  }
  v9 = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      124,
      (unsigned int)WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      (_DWORD)this,
      (__int64)a2);
  BaseHttpListener::IncrThreadCount(this);
  if ( !QueueUserWorkItem(BaseHttpListener::HandleUrlQueueStub, v11, 0x10u) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, LastError);
    }
    BaseHttpListener::DecrThreadCount(this);
    v9 = -2147467259;
    goto LABEL_35;
  }
LABEL_40:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  return v9;
}

```

## disassembly

```asm
0x18001ac40  mov     [rsp+arg_8], rbx
0x18001ac45  mov     [rsp+arg_10], rbp
0x18001ac4a  push    rsi
0x18001ac4b  push    rdi
0x18001ac4c  push    r13
0x18001ac4e  push    r14
0x18001ac50  push    r15
0x18001ac52  sub     rsp, 30h
0x18001ac56  mov     edi, r8d
0x18001ac59  mov     r14, rdx
0x18001ac5c  mov     rbp, rcx
0x18001ac5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac66  lea     r13, WPP_GLOBAL_Control
0x18001ac6d  lea     rsi, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001ac74  cmp     rcx, r13
0x18001ac77  jz      short loc_18001AC93
0x18001ac79  test    dword ptr [rcx+1Ch], 100h
0x18001ac80  jz      short loc_18001AC93
0x18001ac82  mov     rcx, [rcx+10h]
0x18001ac86  mov     edx, 76h ; 'v'
0x18001ac8b  mov     r8, rsi
0x18001ac8e  call    WPP_SF_
0x18001ac93  lea     r15, [rbp+0E0h]
0x18001ac9a  mov     rcx, r15; lpCriticalSection
0x18001ac9d  call    cs:__imp_EnterCriticalSection
0x18001aca3  mov     rcx, [rbp+0A8h]
0x18001acaa  lea     r8, [rsp+58h+arg_0]
0x18001acaf  mov     rdx, r14
0x18001acb2  mov     [rsp+58h+arg_0], 0
0x18001acbb  call    ?FindKey@CLKRHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z; LKRhash::CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18001acc0  test    eax, eax
0x18001acc2  jnz     loc_18001AE8F
0x18001acc8  mov     rbx, [rsp+58h+arg_0]
0x18001accd  test    edi, edi
0x18001accf  jz      short loc_18001AD3F
0x18001acd1  mov     dword ptr [rbx+20h], 1
0x18001acd8  cmp     dword ptr [rbx+24h], 0
0x18001acdc  jnz     short loc_18001AD45
0x18001acde  mov     eax, [rbx+28h]
0x18001ace1  test    eax, eax
0x18001ace3  jz      short loc_18001AD0C
0x18001ace5  mov     rdi, cs:WPP_GLOBAL_Control
0x18001acec  cmp     rdi, r13
0x18001acef  jz      short loc_18001AD13
0x18001acf1  test    byte ptr [rdi+1Ch], 1
0x18001acf5  jz      short loc_18001AD13
0x18001acf7  mov     rcx, [rdi+10h]
0x18001acfb  mov     edx, 77h ; 'w'
0x18001ad00  mov     r9d, [rbx+28h]
0x18001ad04  mov     r8, rsi
0x18001ad07  call    WPP_SF_d
0x18001ad0c  mov     rdi, cs:WPP_GLOBAL_Control
0x18001ad13  mov     rdx, [rbx+18h]
0x18001ad17  mov     eax, [rdx+4]
0x18001ad1a  cmp     [rdx], eax
0x18001ad1c  jnz     short loc_18001AD4C
0x18001ad1e  cmp     rdi, r13
0x18001ad21  jz      short loc_18001AD45
0x18001ad23  test    dword ptr [rdi+1Ch], 100h
0x18001ad2a  jz      short loc_18001AD45
0x18001ad2c  mov     rcx, [rdi+10h]
0x18001ad30  mov     edx, 78h ; 'x'
0x18001ad35  mov     r8, rsi
0x18001ad38  call    WPP_SF_
0x18001ad3d  jmp     short loc_18001AD45
0x18001ad3f  cmp     dword ptr [rbx+20h], 0
0x18001ad43  jnz     short loc_18001ACD8
0x18001ad45  xor     ebx, ebx
0x18001ad47  jmp     loc_18001AEB7
0x18001ad4c  mov     ecx, 10h; Size
0x18001ad51  call    cs:__imp_malloc
0x18001ad57  mov     rsi, rax
0x18001ad5a  test    rax, rax
0x18001ad5d  jnz     short loc_18001AD8F
0x18001ad5f  mov     ebx, 8007000Eh
0x18001ad64  cmp     rdi, r13
0x18001ad67  jz      loc_18001AEB7
0x18001ad6d  test    byte ptr [rdi+1Ch], 1
0x18001ad71  jz      loc_18001AEB7
0x18001ad77  mov     rcx, [rdi+10h]
0x18001ad7b  lea     edx, [rax+7Ah]
0x18001ad7e  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001ad85  call    WPP_SF_
0x18001ad8a  jmp     loc_18001AEB7
0x18001ad8f  mov     rdx, r14; char *
0x18001ad92  mov     [rax], rbp
0x18001ad95  lea     rcx, [rax+8]; char **
0x18001ad99  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x18001ad9e  cmp     qword ptr [rsi+8], 0
0x18001ada3  jnz     short loc_18001ADDE
0x18001ada5  mov     ebx, 8007000Eh
0x18001adaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adb1  cmp     rcx, r13
0x18001adb4  jz      loc_18001AE7A
0x18001adba  test    byte ptr [rcx+1Ch], 1
0x18001adbe  jz      loc_18001AE7A
0x18001adc4  mov     rcx, [rcx+10h]
0x18001adc8  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001adcf  mov     edx, 7Bh ; '{'
0x18001add4  call    WPP_SF_
0x18001add9  jmp     loc_18001AE7A
0x18001adde  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ade5  xor     ebx, ebx
0x18001ade7  cmp     rcx, r13
0x18001adea  jz      short loc_18001AE10
0x18001adec  test    dword ptr [rcx+1Ch], 100h
0x18001adf3  jz      short loc_18001AE10
0x18001adf5  mov     rcx, [rcx+10h]
0x18001adf9  lea     edx, [rbx+7Ch]
0x18001adfc  mov     r9, rbp
0x18001adff  mov     [rsp+58h+var_38], r14
0x18001ae04  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001ae0b  call    WPP_SF_qs
0x18001ae10  mov     rcx, rbp; this
0x18001ae13  call    ?IncrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::IncrThreadCount(void)
0x18001ae18  mov     r8d, 10h; Flags
0x18001ae1e  lea     rcx, ?HandleUrlQueueStub@BaseHttpListener@@KAKPEAX@Z; Function
0x18001ae25  mov     rdx, rsi; Context
0x18001ae28  call    cs:__imp_QueueUserWorkItem
0x18001ae2e  test    eax, eax
0x18001ae30  jnz     loc_18001AEB7
0x18001ae36  mov     rax, cs:WPP_GLOBAL_Control
0x18001ae3d  cmp     rax, r13
0x18001ae40  jz      short loc_18001AE6D
0x18001ae42  test    byte ptr [rax+1Ch], 1
0x18001ae46  jz      short loc_18001AE6D
0x18001ae48  call    cs:__imp_GetLastError
0x18001ae4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae55  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001ae5c  mov     edx, 7Dh ; '}'
0x18001ae61  mov     r9d, eax
0x18001ae64  mov     rcx, [rcx+10h]
0x18001ae68  call    WPP_SF_d
0x18001ae6d  mov     rcx, rbp; this
0x18001ae70  call    ?DecrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::DecrThreadCount(void)
0x18001ae75  mov     ebx, 80004005h
0x18001ae7a  mov     rcx, [rsi+8]; Block
0x18001ae7e  call    cs:__imp_free
0x18001ae84  mov     rcx, rsi; Block
0x18001ae87  call    cs:__imp_free
0x18001ae8d  jmp     short loc_18001AEB7
0x18001ae8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae96  cmp     rcx, r13
0x18001ae99  jz      short loc_18001AEB2
0x18001ae9b  test    byte ptr [rcx+1Ch], 1
0x18001ae9f  jz      short loc_18001AEB2
0x18001aea1  mov     rcx, [rcx+10h]
0x18001aea5  mov     edx, 79h ; 'y'
0x18001aeaa  mov     r8, rsi
0x18001aead  call    WPP_SF_
0x18001aeb2  mov     ebx, 80004004h
0x18001aeb7  mov     rcx, r15; lpCriticalSection
0x18001aeba  call    cs:__imp_LeaveCriticalSection
0x18001aec0  mov     rbp, [rsp+58h+arg_10]
0x18001aec5  mov     eax, ebx
0x18001aec7  mov     rbx, [rsp+58h+arg_8]
0x18001aecc  add     rsp, 30h
0x18001aed0  pop     r15
0x18001aed2  pop     r14
0x18001aed4  pop     r13
0x18001aed6  pop     rdi
0x18001aed7  pop     rsi
0x18001aed8  retn
```
