# CVssAsync::DoTrackRevert(void)

- ea: `0x1800051a0`
- end: `0x180005448`
- name: `?DoTrackRevert@CVssAsync@@IEAAXXZ`
- size: `680`
- prototype: `void __fastcall(CVssAsync *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180005f18`

## callees

- `0x18000212c`
- `0x180003748`
- `0x1800039d8`
- `0x1800051a0`
- `0x18000610c`
- `0x180007824`
- `0x180033a8c`
- `0x180033c78`
- `0x1800377c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000535c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000535c`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800052ec`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800052ec`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800052a4`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800052a4`

## string_xrefs

- `0x18000542f`: `CreateWaitableTimerEx(NULL, NULL, 0, TIMER_ALL_ACCESS)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssAsync::DoTrackRevert(CVssAsync *this)
{
  __int64 v2; // r9
  HANDLE WaitableTimer; // rbx
  CVssAsync *v4; // rcx
  const unsigned __int16 *v5; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v6; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v7; // [rsp+60h] [rbp-A0h]
  int v8; // [rsp+68h] [rbp-98h]
  int v9; // [rsp+6Ch] [rbp-94h]
  int v10; // [rsp+70h] [rbp-90h]
  _BYTE v11[120]; // [rsp+78h] [rbp-88h] BYREF
  int v12; // [rsp+F0h] [rbp-10h]
  _QWORD v13[3]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v14; // [rsp+110h] [rbp+10h] BYREF
  __int128 v15; // [rsp+118h] [rbp+18h]
  __int128 v16; // [rsp+128h] [rbp+28h]
  __int16 v17; // [rsp+138h] [rbp+38h]
  __int64 v18; // [rsp+13Ch] [rbp+3Ch]
  __int64 v19; // [rsp+148h] [rbp+48h]
  __int64 v20; // [rsp+150h] [rbp+50h]
  int v21; // [rsp+158h] [rbp+58h]
  __int64 v22; // [rsp+160h] [rbp+60h]
  __int16 v23; // [rsp+168h] [rbp+68h]
  void **v24; // [rsp+170h] [rbp+70h]
  __int64 v25; // [rsp+178h] [rbp+78h]
  LPVOID v26[14]; // [rsp+180h] [rbp+80h] BYREF
  LARGE_INTEGER DueTime; // [rsp+220h] [rbp+120h] BYREF

  v5 = L"base\\stor\\vss\\modules\\softprv\\src\\async.cxx";
  v6 = L"CVssAsync::DoTrackRevert";
  v7 = L"SWPASYNC";
  v8 = 295;
  v9 = 2;
  v10 = 255;
  v12 = 0x1000000;
  memset_0(v11, 0, sizeof(v11));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v26, (__int64)&v5, 0);
  v14 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v25 = 0;
  v24 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v15 = 0;
  v16 = 0;
  LOBYTE(v2) = 1;
  CVssIOCTLChannel::Open(&v14, v26, *((_QWORD *)this + 23), v2, 1, 2, 0);
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  v13[0] = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v13[1] = WaitableTimer;
  if ( !WaitableTimer )
  {
    v5 = L"base\\stor\\vss\\modules\\softprv\\src\\async.cxx";
    v6 = L"CVssAsync::DoTrackRevert";
    v7 = L"SWPASYNC";
    v8 = 305;
    v9 = 2;
    v10 = 255;
    v12 = 0x1000000;
    memset_0(v11, 0, sizeof(v11));
    CVssFunctionTracer::TranslateWin32Error(v26, &v5, L"CreateWaitableTimerEx(NULL, NULL, 0, TIMER_ALL_ACCESS)");
  }
  DueTime.QuadPart = -10000000;
  if ( !SetWaitableTimer(WaitableTimer, &DueTime, 1000, 0, 0, 0) )
  {
    v5 = L"base\\stor\\vss\\modules\\softprv\\src\\async.cxx";
    v6 = L"CVssAsync::DoTrackRevert";
    v7 = L"SWPASYNC";
    v8 = 310;
    v9 = 2;
    v10 = 255;
    v12 = 0x1000000;
    memset_0(v11, 0, sizeof(v11));
    CVssFunctionTracer::TranslateWin32Error(v26, &v5, L"SetWaitableTimer(1000)");
  }
  while ( (int)CVssAsync::TrackRevert(v4, (struct CVssIOCTLChannel *)&v14) >= 0 )
  {
    if ( WaitForSingleObject(WaitableTimer, 0xFFFFFFFF) )
    {
      v5 = L"base\\stor\\vss\\modules\\softprv\\src\\async.cxx";
      v6 = L"CVssAsync::DoTrackRevert";
      v7 = L"SWPASYNC";
      v8 = 315;
      v9 = 2;
      v10 = 255;
      v12 = 0x1000000;
      memset_0(v11, 0, sizeof(v11));
      CVssFunctionTracer::TranslateWin32Error(v26, &v5, L"WaitForSingleObject(INFINITE)");
    }
  }
  CVssAuto<void *,CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(v13);
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v14);
  CVssFunctionTracer::~CVssFunctionTracer(v26);
}

```

## disassembly

```asm
0x1800051a0  mov     [rsp-8+arg_10], rbx
0x1800051a5  mov     [rsp-8+arg_18], rsi
0x1800051aa  push    rbp
0x1800051ab  push    rdi
0x1800051ac  push    r12
0x1800051ae  push    r14
0x1800051b0  push    r15
0x1800051b2  lea     rbp, [rsp-0F0h]
0x1800051ba  sub     rsp, 1F0h
0x1800051c1  mov     rbx, rcx
0x1800051c4  lea     r14, aBaseStorVssMod_7; "base\\stor\\vss\\modules\\softprv\\src"...
0x1800051cb  mov     [rsp+210h+var_1C0], r14
0x1800051d0  lea     r15, aCvssasyncDotra; "CVssAsync::DoTrackRevert"
0x1800051d7  mov     [rsp+210h+var_1B8], r15
0x1800051dc  lea     r12, aSwpasync; "SWPASYNC"
0x1800051e3  mov     [rsp+210h+var_1B0], r12
0x1800051e8  mov     [rsp+210h+var_1A8], 127h
0x1800051f0  mov     esi, 2
0x1800051f5  mov     [rsp+210h+var_1A4], esi
0x1800051f9  mov     [rsp+210h+var_1A0], 0FFh
0x180005201  xor     edi, edi
0x180005203  mov     [rbp+110h+var_120], 1000000h
0x18000520a  xor     edx, edx; Val
0x18000520c  lea     r8d, [rsi+76h]; Size
0x180005210  lea     rcx, [rsp+210h+var_198]; void *
0x180005215  call    memset_0
0x18000521a  xor     r8d, r8d
0x18000521d  lea     rdx, [rsp+210h+var_1C0]
0x180005222  lea     rcx, [rbp+110h+var_90]
0x180005229  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18000522e  nop
0x18000522f  mov     [rbp+110h+var_100], rdi
0x180005233  mov     [rbp+110h+var_D8], di
0x180005237  mov     [rbp+110h+var_D4], rdi
0x18000523b  mov     [rbp+110h+var_C8], rdi
0x18000523f  mov     [rbp+110h+var_C0], rdi
0x180005243  mov     [rbp+110h+var_B8], edi
0x180005246  mov     [rbp+110h+var_B0], rdi
0x18000524a  mov     [rbp+110h+var_A8], di
0x18000524e  mov     [rbp+110h+var_98], rdi
0x180005252  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180005259  mov     [rbp+110h+var_A0], rax
0x18000525d  xorps   xmm0, xmm0
0x180005260  movups  [rbp+110h+var_F8], xmm0
0x180005264  movups  [rbp+110h+var_E8], xmm0
0x180005268  mov     [rsp+210h+var_1D0], 80h
0x180005270  mov     [rsp+210h+var_1E0], edi
0x180005274  mov     [rsp+210h+fResume], esi
0x180005278  mov     byte ptr [rsp+210h+lpArgToCompletionRoutine], 1
0x18000527d  mov     r9b, 1
0x180005280  mov     r8, [rbx+0B8h]
0x180005287  lea     rdx, [rbp+110h+var_90]
0x18000528e  lea     rcx, [rbp+110h+var_100]
0x180005292  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180005297  mov     r9d, 1F0003h; dwDesiredAccess
0x18000529d  xor     r8d, r8d; dwFlags
0x1800052a0  xor     edx, edx; lpTimerName
0x1800052a2  xor     ecx, ecx; lpTimerAttributes
0x1800052a4  call    cs:__imp_CreateWaitableTimerExW
0x1800052aa  mov     rbx, rax
0x1800052ad  lea     rax, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x1800052b4  mov     [rbp+110h+var_118], rax
0x1800052b8  mov     [rbp+110h+var_110], rbx
0x1800052bc  test    rbx, rbx
0x1800052bf  jz      loc_1800053F5
0x1800052c5  mov     qword ptr [rbp+110h+DueTime], 0FFFFFFFFFF676980h
0x1800052d0  mov     [rsp+210h+fResume], edi; fResume
0x1800052d4  mov     [rsp+210h+lpArgToCompletionRoutine], rdi; lpArgToCompletionRoutine
0x1800052d9  xor     r9d, r9d; pfnCompletionRoutine
0x1800052dc  mov     r8d, 3E8h; lPeriod
0x1800052e2  lea     rdx, [rbp+110h+DueTime]; lpDueTime
0x1800052e9  mov     rcx, rbx; hTimer
0x1800052ec  call    cs:__imp_SetWaitableTimer
0x1800052f2  test    eax, eax
0x1800052f4  jnz     short loc_180005349
0x1800052f6  mov     [rsp+210h+var_1C0], r14
0x1800052fb  mov     [rsp+210h+var_1B8], r15
0x180005300  mov     [rsp+210h+var_1B0], r12
0x180005305  mov     [rsp+210h+var_1A8], 136h
0x18000530d  mov     [rsp+210h+var_1A4], esi
0x180005311  mov     [rsp+210h+var_1A0], 0FFh
0x180005319  mov     [rbp+110h+var_120], 1000000h
0x180005320  xor     edx, edx; Val
0x180005322  lea     r8d, [rsi+76h]; Size
0x180005326  lea     rcx, [rsp+210h+var_198]; void *
0x18000532b  call    memset_0
0x180005330  lea     r8, aSetwaitabletim; "SetWaitableTimer(1000)"
0x180005337  lea     rdx, [rsp+210h+var_1C0]
0x18000533c  lea     rcx, [rbp+110h+var_90]
0x180005343  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x180005349  lea     rdx, [rbp+110h+var_100]; struct CVssIOCTLChannel *
0x18000534d  call    ?TrackRevert@CVssAsync@@IEAAHAEAVCVssIOCTLChannel@@@Z; CVssAsync::TrackRevert(CVssIOCTLChannel &)
0x180005352  test    eax, eax
0x180005354  js      short loc_1800053B9
0x180005356  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005359  mov     rcx, rbx; hHandle
0x18000535c  call    cs:__imp_WaitForSingleObject
0x180005362  test    eax, eax
0x180005364  jz      short loc_180005349
0x180005366  mov     [rsp+210h+var_1C0], r14
0x18000536b  mov     [rsp+210h+var_1B8], r15
0x180005370  mov     [rsp+210h+var_1B0], r12
0x180005375  mov     [rsp+210h+var_1A8], 13Bh
0x18000537d  mov     [rsp+210h+var_1A4], esi
0x180005381  mov     [rsp+210h+var_1A0], 0FFh
0x180005389  mov     [rbp+110h+var_120], 1000000h
0x180005390  xor     edx, edx; Val
0x180005392  lea     r8d, [rdx+78h]; Size
0x180005396  lea     rcx, [rsp+210h+var_198]; void *
0x18000539b  call    memset_0
0x1800053a0  lea     r8, aWaitforsingleo_1; "WaitForSingleObject(INFINITE)"
0x1800053a7  lea     rdx, [rsp+210h+var_1C0]
0x1800053ac  lea     rcx, [rbp+110h+var_90]
0x1800053b3  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1800053b9  lea     rcx, [rbp+110h+var_118]
0x1800053bd  call    ??1?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CVssAuto<void *,CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x1800053c2  nop
0x1800053c3  lea     rcx, [rbp+110h+var_100]; this
0x1800053c7  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x1800053cc  nop
0x1800053cd  lea     rcx, [rbp+110h+var_90]; this
0x1800053d4  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800053d9  lea     r11, [rsp+210h+var_20]
0x1800053e1  mov     rbx, [r11+40h]
0x1800053e5  mov     rsi, [r11+48h]
0x1800053e9  mov     rsp, r11
0x1800053ec  pop     r15
0x1800053ee  pop     r14
0x1800053f0  pop     r12
0x1800053f2  pop     rdi
0x1800053f3  pop     rbp
0x1800053f4  retn
0x1800053f5  mov     [rsp+210h+var_1C0], r14
0x1800053fa  mov     [rsp+210h+var_1B8], r15
0x1800053ff  mov     [rsp+210h+var_1B0], r12
0x180005404  mov     [rsp+210h+var_1A8], 131h
0x18000540c  mov     [rsp+210h+var_1A4], esi
0x180005410  mov     [rsp+210h+var_1A0], 0FFh
0x180005418  mov     [rbp+110h+var_120], 1000000h
0x18000541f  xor     edx, edx; Val
0x180005421  lea     r8d, [rdx+78h]; Size
0x180005425  lea     rcx, [rsp+210h+var_198]; void *
0x18000542a  call    memset_0
0x18000542f  lea     r8, aCreatewaitable_0; "CreateWaitableTimerEx(NULL, NULL, 0, TI"...
0x180005436  lea     rdx, [rsp+210h+var_1C0]
0x18000543b  lea     rcx, [rbp+110h+var_90]
0x180005442  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
```
