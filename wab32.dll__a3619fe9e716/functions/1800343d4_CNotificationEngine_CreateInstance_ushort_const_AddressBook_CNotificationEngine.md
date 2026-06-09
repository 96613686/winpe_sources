# CNotificationEngine::CreateInstance(ushort const *,AddressBook *,CNotificationEngine * *)

- ea: `0x1800343d4`
- end: `0x1800345c0`
- name: `?CreateInstance@CNotificationEngine@@SAJPEBGPEAVAddressBook@@PEAPEAV1@@Z`
- size: `492`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct AddressBook *, struct CNotificationEngine **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800198b0`

## callees

- `0x18000161c`
- `0x1800045e4`
- `0x180005d08`
- `0x180019640`
- `0x1800343d4`
- `0x18008ecc8`
- `0x180091eaa`
- `0x180093010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180034577`
- `KERNEL32!CreateThread` at `0x180034577`
- `KERNEL32!CreateEventW` at `0x18003454a`
- `KERNEL32!CreateEventW` at `0x18003454a`
- `KERNEL32!InitializeCriticalSection` at `0x18003446f`
- `KERNEL32!InitializeCriticalSection` at `0x18003446f`
- `USER32!RegisterClassW` at `0x1800344d5`
- `USER32!RegisterClassW` at `0x1800344d5`
- `USER32!GetClassInfoW` at `0x18003449e`
- `USER32!GetClassInfoW` at `0x18003449e`

## pseudocode

```c
__int64 __fastcall CNotificationEngine::CreateInstance(
        const unsigned __int16 *a1,
        struct AddressBook *a2,
        struct CNotificationEngine **a3)
{
  _QWORD *v6; // rbx
  __int64 v7; // rdi
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 Window; // rax
  unsigned int LastError; // ebx
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-C8h]
  int lpThreadId; // [rsp+28h] [rbp-C0h]
  int v21; // [rsp+30h] [rbp-B8h]
  int v22; // [rsp+38h] [rbp-B0h]
  int v23; // [rsp+40h] [rbp-A8h]
  int v24; // [rsp+48h] [rbp-A0h]
  struct tagWNDCLASSW WndClass; // [rsp+60h] [rbp-88h] BYREF
  _QWORD *v26; // [rsp+100h] [rbp+18h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  v26 = 0;
  if ( !a3 || !a1 || !a2 )
  {
    LastError = -2147024809;
    goto LABEL_19;
  }
  v6 = operator new(0x68u);
  if ( !v6 )
    goto LABEL_17;
  v6[1] = 0;
  v7 = -1;
  *v6 = &CNotificationEngine::`vftable';
  v6[3] = -1;
  v6[4] = -1;
  v6[2] = 0;
  v6[5] = 0;
  v6[11] = 0;
  *((_DWORD *)v6 + 24) = 1;
  v26 = v6;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 6));
  v6[11] = a2;
  (*(void (__fastcall **)(struct AddressBook *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( !GetClassInfoW(hinstMapiXWAB, aContactsNotifi, &WndClass) )
  {
    WndClass.hInstance = hinstMapiXWAB;
    WndClass.lpfnWndProc = (WNDPROC)NotificationWndProc;
    WndClass.style = 0x4000;
    WndClass.lpszClassName = aContactsNotifi;
    RegisterClassW(&WndClass);
  }
  Window = SHFusionCreateWindow(v9, v8, v10, v11, dwCreationFlags, lpThreadId, v21, v22, v23, v24, v6);
  v6[1] = Window;
  if ( !Window )
    goto LABEL_8;
  v14 = -1;
  do
    ++v14;
  while ( a1[v14] );
  v15 = (unsigned __int16 *)operator new(saturated_mul(v14 + 1, 2u));
  v6[2] = v15;
  if ( !v15 )
  {
LABEL_17:
    LastError = -2147024882;
    goto LABEL_19;
  }
  do
    ++v7;
  while ( a1[v7] );
  StringCchCopyW(v15, v7 + 1, a1);
  EventW = CreateEventW(0, 1, 0, 0);
  v6[3] = EventW;
  if ( EventW )
  {
    Thread = CreateThread(0, 0, NotificationThreadProc, v6, 0, 0);
    v6[4] = Thread;
    if ( Thread )
    {
      *a3 = (struct CNotificationEngine *)v6;
      LastError = 0;
      v26 = 0;
      goto LABEL_19;
    }
  }
LABEL_8:
  LastError = HrGetLastError();
LABEL_19:
  OE_SafeReleaseAndNullPtr<CNotificationEngine>(&v26);
  return LastError;
}

```

## disassembly

```asm
0x1800343d4  push    rbx
0x1800343d6  push    rbp
0x1800343d7  push    rsi
0x1800343d8  push    rdi
0x1800343d9  push    r14
0x1800343db  push    r15
0x1800343dd  sub     rsp, 0B8h
0x1800343e4  mov     r14, rdx
0x1800343e7  mov     r15, r8
0x1800343ea  xor     edx, edx; Val
0x1800343ec  mov     rsi, rcx
0x1800343ef  lea     rcx, [rsp+0E8h+WndClass]; void *
0x1800343f4  lea     r8d, [rdx+48h]; Size
0x1800343f8  call    memset_0
0x1800343fd  xor     ebp, ebp
0x1800343ff  mov     [rsp+0E8h+arg_10], rbp
0x180034407  test    r15, r15
0x18003440a  jz      loc_18003459C
0x180034410  test    rsi, rsi
0x180034413  jz      loc_18003459C
0x180034419  test    r14, r14
0x18003441c  jz      loc_18003459C
0x180034422  lea     ecx, [rbp+68h]; Size
0x180034425  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003442a  mov     rbx, rax
0x18003442d  test    rax, rax
0x180034430  jz      loc_180034595
0x180034436  lea     rax, ??_7CNotificationEngine@@6B@; const CNotificationEngine::`vftable'
0x18003443d  mov     [rbx+8], rbp
0x180034441  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180034445  mov     [rbx], rax
0x180034448  lea     rcx, [rbx+30h]; lpCriticalSection
0x18003444c  mov     [rbx+18h], rdi
0x180034450  mov     [rbx+20h], rdi
0x180034454  mov     [rbx+10h], rbp
0x180034458  mov     [rbx+28h], rbp
0x18003445c  mov     [rbx+58h], rbp
0x180034460  mov     dword ptr [rbx+60h], 1
0x180034467  mov     [rsp+0E8h+arg_10], rbx
0x18003446f  call    cs:__imp_InitializeCriticalSection
0x180034475  mov     [rbx+58h], r14
0x180034479  mov     rcx, r14
0x18003447c  mov     rax, [r14]
0x18003447f  mov     rax, [rax+8]
0x180034483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034488  mov     rcx, cs:hinstMapiXWAB; hInstance
0x18003448f  lea     r14, aContactsNotifi; "Contacts Notification Engine"
0x180034496  mov     rdx, r14; lpClassName
0x180034499  lea     r8, [rsp+0E8h+WndClass]; lpWndClass
0x18003449e  call    cs:__imp_GetClassInfoW
0x1800344a4  test    eax, eax
0x1800344a6  jnz     short loc_1800344DB
0x1800344a8  mov     rax, cs:hinstMapiXWAB
0x1800344af  lea     rcx, [rsp+0E8h+WndClass]; lpWndClass
0x1800344b4  mov     [rsp+0E8h+WndClass.hInstance], rax
0x1800344b9  lea     rax, ?NotificationWndProc@@YA_JPEAUHWND__@@I_K_J@Z; NotificationWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800344c0  mov     [rsp+0E8h+WndClass.lpfnWndProc], rax
0x1800344c5  mov     [rsp+0E8h+WndClass.style], 4000h
0x1800344cd  mov     [rsp+0E8h+WndClass.lpszClassName], r14
0x1800344d5  call    cs:__imp_RegisterClassW
0x1800344db  mov     [rsp+0E8h+var_98], rbx; LPVOID
0x1800344e0  call    SHFusionCreateWindow
0x1800344e5  mov     [rbx+8], rax
0x1800344e9  test    rax, rax
0x1800344ec  jnz     short loc_1800344FA
0x1800344ee  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800344f3  mov     ebx, eax
0x1800344f5  jmp     loc_1800345A1
0x1800344fa  mov     rcx, rdi
0x1800344fd  inc     rcx
0x180034500  cmp     [rsi+rcx*2], bp
0x180034504  jnz     short loc_1800344FD
0x180034506  inc     rcx
0x180034509  mov     eax, 2
0x18003450e  mul     rcx
0x180034511  cmovb   rax, rdi
0x180034515  mov     rcx, rax; Size
0x180034518  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003451d  mov     [rbx+10h], rax
0x180034521  test    rax, rax
0x180034524  jz      short loc_180034595
0x180034526  inc     rdi
0x180034529  cmp     [rsi+rdi*2], bp
0x18003452d  jnz     short loc_180034526
0x18003452f  lea     rdx, [rdi+1]; unsigned __int64
0x180034533  mov     r8, rsi; unsigned __int16 *
0x180034536  mov     rcx, rax; unsigned __int16 *
0x180034539  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003453e  xor     r9d, r9d; lpName
0x180034541  xor     r8d, r8d; bInitialState
0x180034544  xor     ecx, ecx; lpEventAttributes
0x180034546  lea     edx, [r9+1]; bManualReset
0x18003454a  call    cs:__imp_CreateEventW
0x180034550  mov     [rbx+18h], rax
0x180034554  test    rax, rax
0x180034557  jnz     short loc_180034560
0x180034559  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18003455e  jmp     short loc_1800344F3
0x180034560  mov     [rsp+0E8h+lpThreadId], rbp; lpThreadId
0x180034565  lea     r8, ?NotificationThreadProc@@YAKPEAX@Z; lpStartAddress
0x18003456c  mov     r9, rbx; lpParameter
0x18003456f  mov     [rsp+0E8h+dwCreationFlags], ebp; dwCreationFlags
0x180034573  xor     edx, edx; dwStackSize
0x180034575  xor     ecx, ecx; lpThreadAttributes
0x180034577  call    cs:__imp_CreateThread
0x18003457d  mov     [rbx+20h], rax
0x180034581  test    rax, rax
0x180034584  jz      short loc_180034559
0x180034586  mov     [r15], rbx
0x180034589  mov     ebx, ebp
0x18003458b  mov     [rsp+0E8h+arg_10], rbp
0x180034593  jmp     short loc_1800345A1
0x180034595  mov     ebx, 8007000Eh
0x18003459a  jmp     short loc_1800345A1
0x18003459c  mov     ebx, 80070057h
0x1800345a1  lea     rcx, [rsp+0E8h+arg_10]
0x1800345a9  call    ??$OE_SafeReleaseAndNullPtr@VCNotificationEngine@@@@YAXAEAPEAVCNotificationEngine@@@Z; OE_SafeReleaseAndNullPtr<CNotificationEngine>(CNotificationEngine * &)
0x1800345ae  mov     eax, ebx
0x1800345b0  add     rsp, 0B8h
0x1800345b7  pop     r15
0x1800345b9  pop     r14
0x1800345bb  pop     rdi
0x1800345bc  pop     rsi
0x1800345bd  pop     rbp
0x1800345be  pop     rbx
0x1800345bf  retn
```
