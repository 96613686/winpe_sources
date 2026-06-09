# BaseHttpListener::SpawnQueueWorkerThread(char const *,int)

- ea: `0x18001bfa0`
- end: `0x18001c264`
- name: `?SpawnQueueWorkerThread@BaseHttpListener@@IEAAJPEBDH@Z`
- size: `708`
- prototype: `__int64 __fastcall(BaseHttpListener *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001b8b4`
- `0x18001bee0`

## callees

- `0x18001bfa0`
- `0x18001c26c`
- `0x1800234d8`
- `0x180025d44`
- `0x1800271fc`
- `0x180029df0`
- `0x1800312cc`
- `0x1800341cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c1f6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c205`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c1f6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c205`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c0b7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c0b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c23e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c23e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bffd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c1ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c1ba`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001c194`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001c194`

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
0x18001bfa0  mov     [rsp+arg_8], rbx
0x18001bfa5  mov     [rsp+arg_10], rbp
0x18001bfaa  push    rsi
0x18001bfab  push    rdi
0x18001bfac  push    r13
0x18001bfae  push    r14
0x18001bfb0  push    r15
0x18001bfb2  sub     rsp, 30h
0x18001bfb6  mov     edi, r8d
0x18001bfb9  mov     r14, rdx
0x18001bfbc  mov     rbp, rcx
0x18001bfbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfc6  lea     r13, WPP_GLOBAL_Control
0x18001bfcd  lea     rsi, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001bfd4  cmp     rcx, r13
0x18001bfd7  jz      short loc_18001BFF3
0x18001bfd9  test    dword ptr [rcx+1Ch], 100h
0x18001bfe0  jz      short loc_18001BFF3
0x18001bfe2  mov     rcx, [rcx+10h]
0x18001bfe6  mov     edx, 76h ; 'v'
0x18001bfeb  mov     r8, rsi
0x18001bfee  call    WPP_SF_
0x18001bff3  lea     r15, [rbp+0E0h]
0x18001bffa  mov     rcx, r15; lpCriticalSection
0x18001bffd  call    cs:__imp_EnterCriticalSection
0x18001c004  nop     dword ptr [rax+rax+00h]
0x18001c009  mov     rcx, [rbp+0A8h]
0x18001c010  lea     r8, [rsp+58h+arg_0]
0x18001c015  mov     rdx, r14
0x18001c018  mov     [rsp+58h+arg_0], 0
0x18001c021  call    ?FindKey@CLKRHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z; LKRhash::CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18001c026  test    eax, eax
0x18001c028  jnz     loc_18001C213
0x18001c02e  mov     rbx, [rsp+58h+arg_0]
0x18001c033  test    edi, edi
0x18001c035  jz      short loc_18001C0A5
0x18001c037  mov     dword ptr [rbx+20h], 1
0x18001c03e  cmp     dword ptr [rbx+24h], 0
0x18001c042  jnz     short loc_18001C0AB
0x18001c044  mov     eax, [rbx+28h]
0x18001c047  test    eax, eax
0x18001c049  jz      short loc_18001C072
0x18001c04b  mov     rdi, cs:WPP_GLOBAL_Control
0x18001c052  cmp     rdi, r13
0x18001c055  jz      short loc_18001C079
0x18001c057  test    byte ptr [rdi+1Ch], 1
0x18001c05b  jz      short loc_18001C079
0x18001c05d  mov     rcx, [rdi+10h]
0x18001c061  mov     edx, 77h ; 'w'
0x18001c066  mov     r9d, [rbx+28h]
0x18001c06a  mov     r8, rsi
0x18001c06d  call    WPP_SF_d
0x18001c072  mov     rdi, cs:WPP_GLOBAL_Control
0x18001c079  mov     rdx, [rbx+18h]
0x18001c07d  mov     eax, [rdx+4]
0x18001c080  cmp     [rdx], eax
0x18001c082  jnz     short loc_18001C0B2
0x18001c084  cmp     rdi, r13
0x18001c087  jz      short loc_18001C0AB
0x18001c089  test    dword ptr [rdi+1Ch], 100h
0x18001c090  jz      short loc_18001C0AB
0x18001c092  mov     rcx, [rdi+10h]
0x18001c096  mov     edx, 78h ; 'x'
0x18001c09b  mov     r8, rsi
0x18001c09e  call    WPP_SF_
0x18001c0a3  jmp     short loc_18001C0AB
0x18001c0a5  cmp     dword ptr [rbx+20h], 0
0x18001c0a9  jnz     short loc_18001C03E
0x18001c0ab  xor     ebx, ebx
0x18001c0ad  jmp     loc_18001C23B
0x18001c0b2  mov     ecx, 10h; Size
0x18001c0b7  call    cs:__imp_malloc
0x18001c0be  nop     dword ptr [rax+rax+00h]
0x18001c0c3  mov     rsi, rax
0x18001c0c6  test    rax, rax
0x18001c0c9  jnz     short loc_18001C0FB
0x18001c0cb  mov     ebx, 8007000Eh
0x18001c0d0  cmp     rdi, r13
0x18001c0d3  jz      loc_18001C23B
0x18001c0d9  test    byte ptr [rdi+1Ch], 1
0x18001c0dd  jz      loc_18001C23B
0x18001c0e3  mov     rcx, [rdi+10h]
0x18001c0e7  lea     edx, [rax+7Ah]
0x18001c0ea  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001c0f1  call    WPP_SF_
0x18001c0f6  jmp     loc_18001C23B
0x18001c0fb  mov     rdx, r14; char *
0x18001c0fe  mov     [rax], rbp
0x18001c101  lea     rcx, [rax+8]; char **
0x18001c105  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x18001c10a  cmp     qword ptr [rsi+8], 0
0x18001c10f  jnz     short loc_18001C14A
0x18001c111  mov     ebx, 8007000Eh
0x18001c116  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c11d  cmp     rcx, r13
0x18001c120  jz      loc_18001C1F2
0x18001c126  test    byte ptr [rcx+1Ch], 1
0x18001c12a  jz      loc_18001C1F2
0x18001c130  mov     rcx, [rcx+10h]
0x18001c134  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001c13b  mov     edx, 7Bh ; '{'
0x18001c140  call    WPP_SF_
0x18001c145  jmp     loc_18001C1F2
0x18001c14a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c151  xor     ebx, ebx
0x18001c153  cmp     rcx, r13
0x18001c156  jz      short loc_18001C17C
0x18001c158  test    dword ptr [rcx+1Ch], 100h
0x18001c15f  jz      short loc_18001C17C
0x18001c161  mov     rcx, [rcx+10h]
0x18001c165  lea     edx, [rbx+7Ch]
0x18001c168  mov     r9, rbp
0x18001c16b  mov     [rsp+58h+var_38], r14
0x18001c170  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001c177  call    WPP_SF_qs
0x18001c17c  mov     rcx, rbp; this
0x18001c17f  call    ?IncrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::IncrThreadCount(void)
0x18001c184  mov     r8d, 10h; Flags
0x18001c18a  lea     rcx, ?HandleUrlQueueStub@BaseHttpListener@@KAKPEAX@Z; Function
0x18001c191  mov     rdx, rsi; Context
0x18001c194  call    cs:__imp_QueueUserWorkItem
0x18001c19b  nop     dword ptr [rax+rax+00h]
0x18001c1a0  test    eax, eax
0x18001c1a2  jnz     loc_18001C23B
0x18001c1a8  mov     rax, cs:WPP_GLOBAL_Control
0x18001c1af  cmp     rax, r13
0x18001c1b2  jz      short loc_18001C1E5
0x18001c1b4  test    byte ptr [rax+1Ch], 1
0x18001c1b8  jz      short loc_18001C1E5
0x18001c1ba  call    cs:__imp_GetLastError
0x18001c1c1  nop     dword ptr [rax+rax+00h]
0x18001c1c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1cd  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001c1d4  mov     edx, 7Dh ; '}'
0x18001c1d9  mov     r9d, eax
0x18001c1dc  mov     rcx, [rcx+10h]
0x18001c1e0  call    WPP_SF_d
0x18001c1e5  mov     rcx, rbp; this
0x18001c1e8  call    ?DecrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::DecrThreadCount(void)
0x18001c1ed  mov     ebx, 80004005h
0x18001c1f2  mov     rcx, [rsi+8]; Block
0x18001c1f6  call    cs:__imp_free
0x18001c1fd  nop     dword ptr [rax+rax+00h]
0x18001c202  mov     rcx, rsi; Block
0x18001c205  call    cs:__imp_free
0x18001c20c  nop     dword ptr [rax+rax+00h]
0x18001c211  jmp     short loc_18001C23B
0x18001c213  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c21a  cmp     rcx, r13
0x18001c21d  jz      short loc_18001C236
0x18001c21f  test    byte ptr [rcx+1Ch], 1
0x18001c223  jz      short loc_18001C236
0x18001c225  mov     rcx, [rcx+10h]
0x18001c229  mov     edx, 79h ; 'y'
0x18001c22e  mov     r8, rsi
0x18001c231  call    WPP_SF_
0x18001c236  mov     ebx, 80004004h
0x18001c23b  mov     rcx, r15; lpCriticalSection
0x18001c23e  call    cs:__imp_LeaveCriticalSection
0x18001c245  nop     dword ptr [rax+rax+00h]
0x18001c24a  mov     rbp, [rsp+58h+arg_10]
0x18001c24f  mov     eax, ebx
0x18001c251  mov     rbx, [rsp+58h+arg_8]
0x18001c256  add     rsp, 30h
0x18001c25a  pop     r15
0x18001c25c  pop     r14
0x18001c25e  pop     r13
0x18001c260  pop     rdi
0x18001c261  pop     rsi
0x18001c262  retn
```
