# CHungApp::~CHungApp(void)

- ea: `0x180025f00`
- end: `0x1800261ef`
- name: `??1CHungApp@@QEAA@XZ`
- size: `751`
- prototype: `void __fastcall(struct _TP_WAIT **this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180013df4`
- `0x180025f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800261e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026124`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002613a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002617c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026124`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002613a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002617c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260a2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002610e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260a2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800260fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002610e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800261ba`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800261ba`

## pseudocode

```c
void __fastcall CHungApp::~CHungApp(struct _TP_WAIT **this)
{
  struct _TP_WAIT *v2; // rcx
  struct _TP_WAIT *v3; // rcx
  struct _TP_WAIT *v4; // rcx
  struct _TP_WAIT *v5; // rcx
  struct _TP_WAIT *v6; // rcx
  struct _TP_WAIT *v7; // rcx
  struct _TP_WAIT *v8; // rcx
  struct _TP_WAIT *v9; // rcx
  struct _TP_WAIT *v10; // rcx
  struct _TP_WAIT *v11; // rcx
  struct _TP_WAIT *v12; // rcx
  struct _TP_WAIT *v13; // rcx
  struct _TP_WAIT *v14; // rcx
  struct _TP_WAIT *v15; // rcx
  struct _TP_WAIT *v16; // rcx
  struct _TP_WAIT *v17; // rcx

  if ( *((_DWORD *)this + 12) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 13) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 229) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (unsigned __int64)this[43] + 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( this[5] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 82) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 613) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( this[44] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (unsigned __int64)this[46] + 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (unsigned __int64)this[47] + 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (unsigned __int64)this[48] + 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (unsigned __int64)this[45] + 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (unsigned __int64)this[148] + 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (unsigned __int64)this[297] + 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (unsigned __int64)this[296] + 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( this[298] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( this[299] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( this[300] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( this[301] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( this[302] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( this[303] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( this[304] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 612) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 611) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 610) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  v2 = this[304];
  if ( v2 )
    CloseThreadpoolWait(v2);
  v3 = this[303];
  if ( v3 )
    CloseThreadpoolWait(v3);
  v4 = this[302];
  if ( v4 )
    CloseThreadpoolWait(v4);
  v5 = this[301];
  if ( v5 )
    CloseThreadpoolWait(v5);
  v6 = this[300];
  if ( v6 )
    CloseThreadpoolWait(v6);
  v7 = this[299];
  if ( v7 )
    CloseThreadpoolWait(v7);
  v8 = this[298];
  if ( v8 )
    CloseThreadpoolWait(v8);
  v9 = this[297];
  if ( (unsigned __int64)v9 + 1 > 1 )
    CloseHandle(v9);
  v10 = this[296];
  if ( (unsigned __int64)v10 + 1 > 1 )
    CloseHandle(v10);
  v11 = this[148];
  if ( (unsigned __int64)v11 + 1 > 1 )
    CloseHandle(v11);
  v12 = this[48];
  if ( (unsigned __int64)v12 + 1 > 1 )
    CloseHandle(v12);
  v13 = this[47];
  if ( (unsigned __int64)v13 + 1 > 1 )
    CloseHandle(v13);
  v14 = this[46];
  if ( (unsigned __int64)v14 + 1 > 1 )
    CloseHandle(v14);
  v15 = this[45];
  if ( (unsigned __int64)v15 + 1 > 1 )
    CloseHandle(v15);
  v16 = this[44];
  if ( v16 )
    UnmapViewOfFile(v16);
  v17 = this[43];
  if ( (unsigned __int64)v17 + 1 > 1 )
    CloseHandle(v17);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180025f00  mov     [rsp+arg_0], rbx
0x180025f05  mov     [rsp+arg_8], rsi
0x180025f0a  push    rdi
0x180025f0b  sub     rsp, 20h
0x180025f0f  mov     rbx, rcx
0x180025f12  xor     esi, esi
0x180025f14  cmp     [rcx+30h], esi
0x180025f17  jz      short loc_180025F1E
0x180025f19  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f1e  cmp     [rbx+34h], esi
0x180025f21  jz      short loc_180025F28
0x180025f23  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f28  cmp     [rbx+394h], esi
0x180025f2e  jz      short loc_180025F35
0x180025f30  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f35  mov     rax, [rbx+158h]
0x180025f3c  mov     edi, 1
0x180025f41  add     rax, rdi
0x180025f44  cmp     rax, rdi
0x180025f47  jbe     short loc_180025F4E
0x180025f49  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f4e  cmp     [rbx+28h], rsi
0x180025f52  jz      short loc_180025F59
0x180025f54  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f59  cmp     [rbx+148h], esi
0x180025f5f  jz      short loc_180025F66
0x180025f61  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f66  cmp     [rbx+994h], esi
0x180025f6c  jz      short loc_180025F73
0x180025f6e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f73  cmp     [rbx+160h], rsi
0x180025f7a  jz      short loc_180025F81
0x180025f7c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f81  mov     rax, [rbx+170h]
0x180025f88  add     rax, rdi
0x180025f8b  cmp     rax, rdi
0x180025f8e  jbe     short loc_180025F95
0x180025f90  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f95  mov     rax, [rbx+178h]
0x180025f9c  add     rax, rdi
0x180025f9f  cmp     rax, rdi
0x180025fa2  jbe     short loc_180025FA9
0x180025fa4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025fa9  mov     rax, [rbx+180h]
0x180025fb0  add     rax, rdi
0x180025fb3  cmp     rax, rdi
0x180025fb6  jbe     short loc_180025FBD
0x180025fb8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025fbd  mov     rax, [rbx+168h]
0x180025fc4  add     rax, rdi
0x180025fc7  cmp     rax, rdi
0x180025fca  jbe     short loc_180025FD1
0x180025fcc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025fd1  mov     rax, [rbx+4A0h]
0x180025fd8  add     rax, rdi
0x180025fdb  cmp     rax, rdi
0x180025fde  jbe     short loc_180025FE5
0x180025fe0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025fe5  mov     rax, [rbx+948h]
0x180025fec  add     rax, rdi
0x180025fef  cmp     rax, rdi
0x180025ff2  jbe     short loc_180025FF9
0x180025ff4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025ff9  mov     rax, [rbx+940h]
0x180026000  add     rax, rdi
0x180026003  cmp     rax, rdi
0x180026006  jbe     short loc_18002600D
0x180026008  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002600d  cmp     [rbx+950h], rsi
0x180026014  jz      short loc_18002601B
0x180026016  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002601b  cmp     [rbx+958h], rsi
0x180026022  jz      short loc_180026029
0x180026024  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026029  cmp     [rbx+960h], rsi
0x180026030  jz      short loc_180026037
0x180026032  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026037  cmp     [rbx+968h], rsi
0x18002603e  jz      short loc_180026045
0x180026040  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026045  cmp     [rbx+970h], rsi
0x18002604c  jz      short loc_180026053
0x18002604e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026053  cmp     [rbx+978h], rsi
0x18002605a  jz      short loc_180026061
0x18002605c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026061  cmp     [rbx+980h], rsi
0x180026068  jz      short loc_18002606F
0x18002606a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002606f  cmp     [rbx+990h], esi
0x180026075  jz      short loc_18002607C
0x180026077  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002607c  cmp     [rbx+98Ch], esi
0x180026082  jz      short loc_180026089
0x180026084  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026089  cmp     [rbx+988h], esi
0x18002608f  jz      short loc_180026096
0x180026091  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026096  mov     rcx, [rbx+980h]; pwa
0x18002609d  test    rcx, rcx
0x1800260a0  jz      short loc_1800260A8
0x1800260a2  call    cs:__imp_CloseThreadpoolWait
0x1800260a8  mov     rcx, [rbx+978h]; pwa
0x1800260af  test    rcx, rcx
0x1800260b2  jz      short loc_1800260BA
0x1800260b4  call    cs:__imp_CloseThreadpoolWait
0x1800260ba  mov     rcx, [rbx+970h]; pwa
0x1800260c1  test    rcx, rcx
0x1800260c4  jz      short loc_1800260CC
0x1800260c6  call    cs:__imp_CloseThreadpoolWait
0x1800260cc  mov     rcx, [rbx+968h]; pwa
0x1800260d3  test    rcx, rcx
0x1800260d6  jz      short loc_1800260DE
0x1800260d8  call    cs:__imp_CloseThreadpoolWait
0x1800260de  mov     rcx, [rbx+960h]; pwa
0x1800260e5  test    rcx, rcx
0x1800260e8  jz      short loc_1800260F0
0x1800260ea  call    cs:__imp_CloseThreadpoolWait
0x1800260f0  mov     rcx, [rbx+958h]; pwa
0x1800260f7  test    rcx, rcx
0x1800260fa  jz      short loc_180026102
0x1800260fc  call    cs:__imp_CloseThreadpoolWait
0x180026102  mov     rcx, [rbx+950h]; pwa
0x180026109  test    rcx, rcx
0x18002610c  jz      short loc_180026114
0x18002610e  call    cs:__imp_CloseThreadpoolWait
0x180026114  mov     rcx, [rbx+948h]; hObject
0x18002611b  lea     rax, [rcx+1]
0x18002611f  cmp     rax, rdi
0x180026122  jbe     short loc_18002612A
0x180026124  call    cs:__imp_CloseHandle
0x18002612a  mov     rcx, [rbx+940h]; hObject
0x180026131  lea     rax, [rcx+1]
0x180026135  cmp     rax, rdi
0x180026138  jbe     short loc_180026140
0x18002613a  call    cs:__imp_CloseHandle
0x180026140  mov     rcx, [rbx+4A0h]; hObject
0x180026147  lea     rax, [rcx+1]
0x18002614b  cmp     rax, rdi
0x18002614e  jbe     short loc_180026156
0x180026150  call    cs:__imp_CloseHandle
0x180026156  mov     rcx, [rbx+180h]; hObject
0x18002615d  lea     rax, [rcx+1]
0x180026161  cmp     rax, rdi
0x180026164  jbe     short loc_18002616C
0x180026166  call    cs:__imp_CloseHandle
0x18002616c  mov     rcx, [rbx+178h]; hObject
0x180026173  lea     rax, [rcx+1]
0x180026177  cmp     rax, rdi
0x18002617a  jbe     short loc_180026182
0x18002617c  call    cs:__imp_CloseHandle
0x180026182  mov     rcx, [rbx+170h]; hObject
0x180026189  lea     rax, [rcx+1]
0x18002618d  cmp     rax, rdi
0x180026190  jbe     short loc_180026198
0x180026192  call    cs:__imp_CloseHandle
0x180026198  mov     rcx, [rbx+168h]; hObject
0x18002619f  lea     rax, [rcx+1]
0x1800261a3  cmp     rax, rdi
0x1800261a6  jbe     short loc_1800261AE
0x1800261a8  call    cs:__imp_CloseHandle
0x1800261ae  mov     rcx, [rbx+160h]; lpBaseAddress
0x1800261b5  test    rcx, rcx
0x1800261b8  jz      short loc_1800261C0
0x1800261ba  call    cs:__imp_UnmapViewOfFile
0x1800261c0  mov     rcx, [rbx+158h]; hObject
0x1800261c7  lea     rax, [rcx+1]
0x1800261cb  cmp     rax, rdi
0x1800261ce  jbe     short loc_1800261D6
0x1800261d0  call    cs:__imp_CloseHandle
0x1800261d6  mov     rcx, rbx
0x1800261d9  mov     rbx, [rsp+28h+arg_0]
0x1800261de  mov     rsi, [rsp+28h+arg_8]
0x1800261e3  add     rsp, 20h
0x1800261e7  pop     rdi
0x1800261e8  jmp     cs:__imp_DeleteCriticalSection
```
