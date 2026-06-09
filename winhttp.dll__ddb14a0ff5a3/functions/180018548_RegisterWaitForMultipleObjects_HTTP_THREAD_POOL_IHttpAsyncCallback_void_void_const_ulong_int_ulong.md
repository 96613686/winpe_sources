# RegisterWaitForMultipleObjects(HTTP_THREAD_POOL *,IHttpAsyncCallback *,void *,void * const *,ulong,int,ulong)

- ea: `0x180018548`
- end: `0x180018817`
- name: `?RegisterWaitForMultipleObjects@@YAJPEAVHTTP_THREAD_POOL@@PEAVIHttpAsyncCallback@@PEAXPEBQEAXKHK@Z`
- size: `719`
- prototype: `__int64 __usercall@<rax>(struct HTTP_THREAD_POOL *this@<rcx>, struct IHttpAsyncCallback *@<rdx>, void *@<r8>, void *const *@<r9>, unsigned int, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002622c`

## callees

- `0x180018548`
- `0x180018820`
- `0x180018b3c`
- `0x180018ee8`
- `0x180018f44`
- `0x180098320`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001872d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001872d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001860e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001860e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800185b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800185b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018739`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018620`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018620`

## pseudocode

```c
__int64 __fastcall RegisterWaitForMultipleObjects(
        struct HTTP_THREAD_POOL *this,
        struct IHttpAsyncCallback *a2,
        void *a3,
        void *const *a4,
        unsigned int a5,
        int a6,
        unsigned int a7)
{
  struct HTTP_THREAD_POOL::WAIT_CONTEXT *v9; // rsi
  void *v10; // rax
  void *v11; // rdi
  HANDLE EventW; // rax
  unsigned __int64 v13; // r8
  void *v14; // rcx
  HANDLE v15; // rbx
  signed int v16; // ebx
  unsigned int i; // r14d
  int v18; // eax
  struct HTTP_THREAD_POOL::WAIT_CONTEXT *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r14
  __int64 v23; // rsi
  void *v24; // r12
  __int64 v25; // r13
  struct _FILETIME *v26; // r15
  signed int LastError; // eax
  struct HTTP_THREAD_POOL::WAIT_CONTEXT *v29; // [rsp+30h] [rbp-51h] BYREF
  __int64 v30; // [rsp+38h] [rbp-49h] BYREF
  int v31; // [rsp+40h] [rbp-41h] BYREF
  int v32; // [rsp+44h] [rbp-3Dh]
  __int64 v33; // [rsp+48h] [rbp-39h] BYREF
  _BYTE v34[16]; // [rsp+50h] [rbp-31h] BYREF
  __int64 *v35; // [rsp+60h] [rbp-21h]
  __int64 v36; // [rsp+68h] [rbp-19h]
  int *v37; // [rsp+70h] [rbp-11h]
  __int64 v38; // [rsp+78h] [rbp-9h]

  v33 = (__int64)a4;
  v32 = 0;
  v29 = 0;
  v9 = 0;
  if ( this )
  {
    if ( a2 )
    {
      if ( a4 )
      {
        v10 = HeapAlloc(g_hWxProcessHeap, 0, 0x88u);
        v11 = v10;
        if ( v10 )
        {
          memset_0(v10, 0, 0x88u);
          *(_QWORD *)v11 = &MULTI_WAIT_CONTEXT::`vftable';
          *((_DWORD *)v11 + 2) = 1;
          *((_DWORD *)v11 + 3) = 0;
          *((_DWORD *)v11 + 10) = 0;
          *((_QWORD *)v11 + 3) = 0;
          *((_QWORD *)v11 + 4) = 0;
          *((_QWORD *)v11 + 16) = 0;
          *((_QWORD *)v11 + 6) = 0;
          EventW = CreateEventW(0, 1, 0, 0);
          v14 = (void *)*((_QWORD *)v11 + 2);
          v15 = EventW;
          if ( v14 )
            CloseHandle(v14);
          *((_QWORD *)v11 + 2) = v15;
          if ( v15 )
          {
            v16 = 0;
            for ( i = 0; i < 3; ++i )
            {
              v18 = HTTP_THREAD_POOL::CreateWait(this, (struct IHttpAsyncCallback *)v11, v13, &v29);
              v16 = v18;
              if ( v18 > 0 )
                v16 = (unsigned __int16)v18 | 0x80070000;
              if ( v16 < 0 )
              {
                v9 = v29;
                v32 = 1337;
                goto LABEL_25;
              }
              v19 = v29;
              *((_QWORD *)v29 + 3) = v29;
              _InterlockedIncrement((volatile signed __int32 *)v11 + 2);
              ++*((_DWORD *)v11 + 10);
              v20 = i;
              v29 = 0;
              *((_QWORD *)v11 + v20 + 6) = v19;
            }
            v21 = a7;
            v22 = 0;
            v23 = v33;
            *((_QWORD *)v11 + 3) = a2;
            *((_QWORD *)v11 + 4) = 0;
            do
            {
              v24 = *(void **)(v23 + 8 * v22);
              v25 = *((_QWORD *)v11 + v22 + 6);
              v33 = 0;
              if ( (_DWORD)v21 == -1 )
              {
                v26 = 0;
              }
              else
              {
                v26 = (struct _FILETIME *)&v33;
                v33 = -10000 * v21;
              }
              if ( (Microsoft_Windows_WinHttpEnableBits & 8) != 0 )
              {
                v31 = 4;
                v35 = &v30;
                v30 = v25;
                v37 = &v31;
                v36 = 8;
                v38 = 4;
                McGenEventWrite_EtwEventWriteTransfer(
                  WINHTTP_ETW_PROVIDER_ID_Context,
                  (__int64)QueueThreadAction,
                  v13,
                  3,
                  (__int64)v34);
              }
              WxSetThreadpoolWait(*(struct _TP_WAIT **)(v25 + 48), v24, v26);
              v21 = 0xFFFFFFFFLL;
              ++v22;
            }
            while ( v22 != 3 );
            SetEvent(*((HANDLE *)v11 + 2));
            v9 = v29;
          }
          else
          {
            LastError = GetLastError();
            v16 = LastError;
            if ( LastError > 0 )
              v16 = (unsigned __int16)LastError | 0x80070000;
            v32 = 1329;
            if ( v16 >= 0 )
              v16 = -2147418113;
LABEL_25:
            CancelAllWaits((struct MULTI_WAIT_CONTEXT *)v11, 0, v13);
          }
          MULTI_WAIT_CONTEXT::Release((MULTI_WAIT_CONTEXT *)v11);
          if ( v9 )
            (**(void (__fastcall ***)(struct HTTP_THREAD_POOL::WAIT_CONTEXT *, __int64))v9)(v9, 1);
        }
        else
        {
          v16 = -2147024882;
          v32 = 1326;
        }
      }
      else
      {
        v16 = -2147024809;
        v32 = 1322;
      }
    }
    else
    {
      v16 = -2147024809;
      v32 = 1321;
    }
  }
  else
  {
    v16 = -2147024809;
    v32 = 1320;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180018548  mov     [rsp-8+arg_8], rbx
0x18001854d  push    rbp
0x18001854e  push    rsi
0x18001854f  push    rdi
0x180018550  push    r12
0x180018552  push    r13
0x180018554  push    r14
0x180018556  push    r15
0x180018558  lea     rbp, [rsp-0Fh]
0x18001855d  sub     rsp, 90h
0x180018564  mov     rax, cs:__security_cookie
0x18001856b  xor     rax, rsp
0x18001856e  mov     [rbp+3Fh+var_40], rax
0x180018572  xor     r13d, r13d
0x180018575  mov     [rbp+3Fh+var_78], r9
0x180018579  mov     [rbp+3Fh+var_7C], r13d
0x18001857d  mov     r15, rdx
0x180018580  mov     [rbp+3Fh+var_90], r13
0x180018584  mov     r12, rcx
0x180018587  mov     esi, r13d
0x18001858a  test    rcx, rcx
0x18001858d  jz      loc_1800187B7
0x180018593  test    rdx, rdx
0x180018596  jz      loc_1800187E0
0x18001859c  test    r9, r9
0x18001859f  jz      loc_1800187EE
0x1800185a5  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800185ac  mov     ebx, 88h
0x1800185b1  mov     r8d, ebx; dwBytes
0x1800185b4  xor     edx, edx; dwFlags
0x1800185b6  call    cs:__imp_HeapAlloc
0x1800185bc  mov     rdi, rax
0x1800185bf  test    rax, rax
0x1800185c2  jz      loc_1800187D2
0x1800185c8  mov     r8d, ebx; Size
0x1800185cb  xor     edx, edx; Val
0x1800185cd  mov     rcx, rax; void *
0x1800185d0  call    memset_0
0x1800185d5  lea     rax, ??_7MULTI_WAIT_CONTEXT@@6B@; const MULTI_WAIT_CONTEXT::`vftable'
0x1800185dc  mov     [rdi], rax
0x1800185df  xor     eax, eax
0x1800185e1  mov     dword ptr [rdi+8], 1
0x1800185e8  mov     [rdi+0Ch], r13d
0x1800185ec  mov     [rdi+28h], r13d
0x1800185f0  mov     [rdi+18h], r13
0x1800185f4  mov     [rdi+20h], r13
0x1800185f8  mov     [rdi+80h], r13
0x1800185ff  mov     [rdi+30h], rax
0x180018603  xor     r9d, r9d; lpName
0x180018606  lea     edx, [rax+1]; bManualReset
0x180018609  xor     r8d, r8d; bInitialState
0x18001860c  xor     ecx, ecx; lpEventAttributes
0x18001860e  call    cs:__imp_CreateEventW
0x180018614  mov     rcx, [rdi+10h]; hObject
0x180018618  mov     rbx, rax
0x18001861b  test    rcx, rcx
0x18001861e  jz      short loc_180018626
0x180018620  call    cs:__imp_CloseHandle
0x180018626  mov     [rdi+10h], rbx
0x18001862a  test    rbx, rbx
0x18001862d  jz      loc_180018739
0x180018633  mov     ebx, r13d
0x180018636  mov     r14d, r13d
0x180018639  cmp     r14d, 3
0x18001863d  jnb     short loc_180018685
0x18001863f  lea     r9, [rbp+3Fh+var_90]; struct HTTP_THREAD_POOL::WAIT_CONTEXT **
0x180018643  mov     rdx, rdi; struct IHttpAsyncCallback *
0x180018646  mov     rcx, r12; this
0x180018649  call    ?CreateWait@HTTP_THREAD_POOL@@QEAAKPEAVIHttpAsyncCallback@@_KPEAPEAUWAIT_CONTEXT@1@@Z; HTTP_THREAD_POOL::CreateWait(IHttpAsyncCallback *,unsigned __int64,HTTP_THREAD_POOL::WAIT_CONTEXT * *)
0x18001864e  mov     ebx, eax
0x180018650  test    eax, eax
0x180018652  jle     short loc_18001865D
0x180018654  movzx   ebx, ax
0x180018657  or      ebx, 80070000h
0x18001865d  test    ebx, ebx
0x18001865f  js      loc_1800187C5
0x180018665  mov     rcx, [rbp+3Fh+var_90]
0x180018669  mov     [rcx+18h], rcx
0x18001866d  lock inc dword ptr [rdi+8]
0x180018671  inc     dword ptr [rdi+28h]
0x180018674  mov     eax, r14d
0x180018677  inc     r14d
0x18001867a  mov     [rbp+3Fh+var_90], r13
0x18001867e  mov     [rdi+rax*8+30h], rcx
0x180018683  jmp     short loc_180018639
0x180018685  mov     eax, [rbp+3Fh+arg_30]
0x180018688  mov     r14, r13
0x18001868b  mov     rsi, [rbp+3Fh+var_78]
0x18001868f  mov     [rdi+18h], r15
0x180018693  mov     [rdi+20h], r13
0x180018697  mov     r12, [rsi+r14*8]
0x18001869b  mov     r13, [rdi+r14*8+30h]
0x1800186a0  mov     [rbp+3Fh+var_78], 0
0x1800186a8  cmp     eax, 0FFFFFFFFh
0x1800186ab  jnz     loc_1800187A3
0x1800186b1  xor     r15d, r15d
0x1800186b4  test    cs:Microsoft_Windows_WinHttpEnableBits, 8
0x1800186bb  jz      short loc_18001870A
0x1800186bd  lea     rax, [rbp+3Fh+var_88]
0x1800186c1  mov     [rbp+3Fh+var_80], 4
0x1800186c8  mov     [rbp+3Fh+var_60], rax
0x1800186cc  lea     rdx, QueueThreadAction
0x1800186d3  lea     rax, [rbp+3Fh+var_80]
0x1800186d7  mov     [rbp+3Fh+var_88], r13
0x1800186db  mov     [rbp+3Fh+var_50], rax
0x1800186df  lea     rcx, WINHTTP_ETW_PROVIDER_ID_Context
0x1800186e6  lea     rax, [rbp+3Fh+var_70]
0x1800186ea  mov     [rbp+3Fh+var_58], 8
0x1800186f2  mov     r9d, 3
0x1800186f8  mov     [rsp+0C0h+var_A0], rax
0x1800186fd  mov     [rbp+3Fh+var_48], 4
0x180018705  call    McGenEventWrite_EtwEventWriteTransfer
0x18001870a  mov     rcx, [r13+30h]; struct _TP_WAIT *
0x18001870e  mov     r8, r15; struct _FILETIME *
0x180018711  mov     rdx, r12; void *
0x180018714  call    ?WxSetThreadpoolWait@@YAXPEAU_TP_WAIT@@PEAXPEAU_FILETIME@@@Z; WxSetThreadpoolWait(_TP_WAIT *,void *,_FILETIME *)
0x180018719  or      eax, 0FFFFFFFFh
0x18001871c  inc     r14
0x18001871f  cmp     r14, 3
0x180018723  jnz     loc_180018697
0x180018729  mov     rcx, [rdi+10h]; hEvent
0x18001872d  call    cs:__imp_SetEvent
0x180018733  mov     rsi, [rbp+3Fh+var_90]
0x180018737  jmp     short loc_180018769
0x180018739  call    cs:__imp_GetLastError
0x18001873f  mov     ebx, eax
0x180018741  test    eax, eax
0x180018743  jle     short loc_18001874E
0x180018745  movzx   ebx, ax
0x180018748  or      ebx, 80070000h
0x18001874e  test    ebx, ebx
0x180018750  mov     [rbp+3Fh+var_7C], 531h
0x180018757  mov     eax, 8000FFFFh
0x18001875c  cmovns  ebx, eax
0x18001875f  xor     edx, edx; struct HTTP_THREAD_POOL::WAIT_CONTEXT *
0x180018761  mov     rcx, rdi; struct MULTI_WAIT_CONTEXT *
0x180018764  call    ?CancelAllWaits@@YAXPEAVMULTI_WAIT_CONTEXT@@PEAUWAIT_CONTEXT@HTTP_THREAD_POOL@@@Z; CancelAllWaits(MULTI_WAIT_CONTEXT *,HTTP_THREAD_POOL::WAIT_CONTEXT *)
0x180018769  mov     rcx, rdi; this
0x18001876c  call    ?Release@MULTI_WAIT_CONTEXT@@QEAAKXZ; MULTI_WAIT_CONTEXT::Release(void)
0x180018771  test    rsi, rsi
0x180018774  jnz     loc_1800187FF
0x18001877a  mov     eax, ebx
0x18001877c  mov     rcx, [rbp+3Fh+var_40]
0x180018780  xor     rcx, rsp; StackCookie
0x180018783  call    __security_check_cookie
0x180018788  mov     rbx, [rsp+0C0h+arg_8]
0x180018790  add     rsp, 90h
0x180018797  pop     r15
0x180018799  pop     r14
0x18001879b  pop     r13
0x18001879d  pop     r12
0x18001879f  pop     rdi
0x1800187a0  pop     rsi
0x1800187a1  pop     rbp
0x1800187a2  retn
0x1800187a3  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1800187aa  lea     r15, [rbp+3Fh+var_78]
0x1800187ae  mov     [rbp+3Fh+var_78], rcx
0x1800187b2  jmp     loc_1800186B4
0x1800187b7  mov     ebx, 80070057h
0x1800187bc  mov     [rbp+3Fh+var_7C], 528h
0x1800187c3  jmp     short loc_18001877A
0x1800187c5  mov     rsi, [rbp+3Fh+var_90]
0x1800187c9  mov     [rbp+3Fh+var_7C], 539h
0x1800187d0  jmp     short loc_18001875F
0x1800187d2  mov     ebx, 8007000Eh
0x1800187d7  mov     [rbp+3Fh+var_7C], 52Eh
0x1800187de  jmp     short loc_18001877A
0x1800187e0  mov     ebx, 80070057h
0x1800187e5  mov     [rbp+3Fh+var_7C], 529h
0x1800187ec  jmp     short loc_18001877A
0x1800187ee  mov     ebx, 80070057h
0x1800187f3  mov     [rbp+3Fh+var_7C], 52Ah
0x1800187fa  jmp     loc_18001877A
0x1800187ff  mov     rax, [rsi]
0x180018802  mov     edx, 1
0x180018807  mov     rcx, rsi
0x18001880a  mov     rax, [rax]
0x18001880d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018812  jmp     loc_18001877A
```
