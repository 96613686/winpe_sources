# MonitorAwareUIPositioner::MonitorAwareUIPositioner(HWND__ *,int,IUnknown *)

- ea: `0x180014554`
- end: `0x1800147de`
- name: `??0MonitorAwareUIPositioner@@QEAA@PEAUHWND__@@HPEAUIUnknown@@@Z`
- size: `650`
- prototype: `MonitorAwareUIPositioner *__fastcall(MonitorAwareUIPositioner *__hidden this, HWND, int, struct IUnknown *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014f14`
- `0x180014fc0`
- `0x18001d900`

## callees

- `0x1800067a0`
- `0x180008320`
- `0x180014554`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001472e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001472e`
- `USER32!EnumWindows` at `0x180014752`
- `USER32!EnumWindows` at `0x180014752`
- `USER32!GetMonitorInfoW` at `0x1800145cf`
- `USER32!GetMonitorInfoW` at `0x1800146e9`
- `USER32!GetMonitorInfoW` at `0x18001478f`
- `USER32!GetMonitorInfoW` at `0x1800145cf`
- `USER32!GetMonitorInfoW` at `0x1800146e9`
- `USER32!GetMonitorInfoW` at `0x18001478f`
- `USER32!MonitorFromWindow` at `0x1800145a0`
- `USER32!MonitorFromWindow` at `0x180014766`
- `USER32!MonitorFromWindow` at `0x1800145a0`
- `USER32!MonitorFromWindow` at `0x180014766`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
MonitorAwareUIPositioner *__fastcall MonitorAwareUIPositioner::MonitorAwareUIPositioner(
        MonitorAwareUIPositioner *this,
        HWND a2,
        int a3,
        struct IUnknown *a4)
{
  HMONITOR v6; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, GUID *, GUID *, __int64 *); // rbx
  DWORD CurrentProcessId; // eax
  HMONITOR v11; // rax
  __int64 v13; // [rsp+30h] [rbp-19h] BYREF
  HMONITOR hMonitor; // [rsp+38h] [rbp-11h] BYREF
  __int64 v15; // [rsp+40h] [rbp-9h] BYREF
  __int64 v16; // [rsp+48h] [rbp-1h] BYREF
  LPARAM lParam; // [rsp+50h] [rbp+7h] BYREF
  DWORD v18; // [rsp+58h] [rbp+Fh]
  tagMONITORINFO mi; // [rsp+60h] [rbp+17h] BYREF

  lParam = (LPARAM)this;
  *(_DWORD *)this = a3;
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  *((_QWORD *)this + 4) = 0;
  v6 = MonitorFromWindow(*((HWND *)this + 1), 0);
  if ( v6 )
  {
    mi.cbSize = 40;
    memset(&mi.rcMonitor, 0, 36);
    if ( GetMonitorInfoW(v6, &mi) )
    {
      *((_DWORD *)this + 4) = (mi.rcWork.left + mi.rcWork.right) / 2;
      *((_DWORD *)this + 5) = (mi.rcWork.bottom + mi.rcWork.top) / 2;
      *((_BYTE *)this + 24) = 1;
    }
  }
  if ( !*((_BYTE *)this + 24) )
  {
    v15 = 0;
    v13 = 0;
    if ( a4 )
    {
      QueryInterface = a4->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      if ( ((int (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
             a4,
             &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
             &v15) >= 0 )
      {
        v8 = v15;
        v9 = *(int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v15 + 24LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
        if ( v9(v8, &IID_IAppActivationUIInfo, &GUID_abad189d_9fa3_4278_b3ca_8ca448a88dcb, &v13) >= 0 )
        {
          v16 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 32LL))(v13, &v16) >= 0 )
          {
            *((_QWORD *)this + 2) = v16;
LABEL_13:
            *((_BYTE *)this + 24) = 1;
            goto LABEL_14;
          }
          hMonitor = 0;
          if ( (*(int (__fastcall **)(__int64, HMONITOR *))(*(_QWORD *)v13 + 24LL))(v13, &hMonitor) >= 0 )
          {
            mi.cbSize = 40;
            memset(&mi.rcMonitor, 0, 36);
            if ( GetMonitorInfoW(hMonitor, &mi) )
            {
              *((_DWORD *)this + 4) = (mi.rcWork.left + mi.rcWork.right) / 2;
              *((_DWORD *)this + 5) = (mi.rcWork.bottom + mi.rcWork.top) / 2;
              goto LABEL_13;
            }
          }
        }
      }
    }
LABEL_14:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    if ( !*((_BYTE *)this + 24) )
    {
      CurrentProcessId = GetCurrentProcessId();
      hMonitor = 0;
      lParam = (LPARAM)&hMonitor;
      v18 = CurrentProcessId;
      EnumWindows(_lambda_e1b59a74a951869dc8650816fa791795_::_lambda_invoker_cdecl_, (LPARAM)&lParam);
      v11 = hMonitor;
      if ( !hMonitor )
        v11 = MonitorFromWindow(0, 1u);
      mi.cbSize = 40;
      memset(&mi.rcMonitor, 0, 36);
      if ( v11 && GetMonitorInfoW(v11, &mi) )
      {
        *((_DWORD *)this + 4) = (mi.rcWork.left + mi.rcWork.right) / 2;
        *((_DWORD *)this + 5) = (mi.rcWork.bottom + mi.rcWork.top) / 2;
        *((_BYTE *)this + 24) = 1;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180014554  mov     [rsp-8+arg_8], rbx
0x180014559  mov     [rsp-8+arg_10], rsi
0x18001455e  push    rbp
0x18001455f  push    rdi
0x180014560  push    r12
0x180014562  lea     rbp, [rsp-47h]
0x180014567  sub     rsp, 90h
0x18001456e  mov     rax, cs:__security_cookie
0x180014575  xor     rax, rsp
0x180014578  mov     [rbp+57h+var_18], rax
0x18001457c  mov     rdi, r9
0x18001457f  mov     rsi, rcx
0x180014582  mov     [rbp+57h+lParam], rcx
0x180014586  mov     [rcx], r8d
0x180014589  mov     [rcx+8], rdx
0x18001458d  xor     eax, eax
0x18001458f  mov     [rcx+10h], rax
0x180014593  mov     [rcx+18h], al
0x180014596  mov     [rcx+20h], rax
0x18001459a  xor     edx, edx; dwFlags
0x18001459c  mov     rcx, [rcx+8]; hwnd
0x1800145a0  call    cs:__imp_MonitorFromWindow
0x1800145a6  mov     r12d, 2
0x1800145ac  test    rax, rax
0x1800145af  jz      short loc_1800145F7
0x1800145b1  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x1800145b8  xorps   xmm0, xmm0
0x1800145bb  xor     ecx, ecx
0x1800145bd  movups  xmmword ptr [rbp+57h+mi.rcMonitor.left], xmm0
0x1800145c1  movups  xmmword ptr [rbp+57h+mi.rcWork.left], xmm0
0x1800145c5  mov     [rbp+57h+mi.dwFlags], ecx
0x1800145c8  lea     rdx, [rbp+57h+mi]; lpmi
0x1800145cc  mov     rcx, rax; hMonitor
0x1800145cf  call    cs:__imp_GetMonitorInfoW
0x1800145d5  test    eax, eax
0x1800145d7  jz      short loc_1800145F7
0x1800145d9  mov     eax, [rbp+57h+mi.rcWork.right]
0x1800145dc  add     eax, [rbp+57h+mi.rcWork.left]
0x1800145df  cdq
0x1800145e0  idiv    r12d
0x1800145e3  mov     [rsi+10h], eax
0x1800145e6  mov     eax, [rbp+57h+mi.rcWork.top]
0x1800145e9  add     eax, [rbp+57h+mi.rcWork.bottom]
0x1800145ec  cdq
0x1800145ed  idiv    r12d
0x1800145f0  mov     [rsi+14h], eax
0x1800145f3  mov     byte ptr [rsi+18h], 1
0x1800145f7  cmp     byte ptr [rsi+18h], 0
0x1800145fb  jnz     loc_1800147B7
0x180014601  mov     [rbp+57h+var_60], 0
0x180014609  mov     [rbp+57h+var_70], 0
0x180014611  test    rdi, rdi
0x180014614  jz      loc_180014711
0x18001461a  mov     rax, [rdi]
0x18001461d  mov     rbx, [rax]
0x180014620  lea     rcx, [rbp+57h+var_60]
0x180014624  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014629  lea     r8, [rbp+57h+var_60]
0x18001462d  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x180014634  mov     rcx, rdi
0x180014637  mov     rax, rbx
0x18001463a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001463f  test    eax, eax
0x180014641  js      loc_180014711
0x180014647  mov     rdi, [rbp+57h+var_60]
0x18001464b  mov     rax, [rdi]
0x18001464e  mov     rbx, [rax+18h]
0x180014652  lea     rcx, [rbp+57h+var_70]
0x180014656  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001465b  lea     r9, [rbp+57h+var_70]
0x18001465f  lea     r8, _GUID_abad189d_9fa3_4278_b3ca_8ca448a88dcb
0x180014666  lea     rdx, IID_IAppActivationUIInfo
0x18001466d  mov     rcx, rdi
0x180014670  mov     rax, rbx
0x180014673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014678  test    eax, eax
0x18001467a  js      loc_180014711
0x180014680  mov     [rbp+57h+var_58], 0
0x180014688  mov     rcx, [rbp+57h+var_70]
0x18001468c  mov     rax, [rcx]
0x18001468f  lea     rdx, [rbp+57h+var_58]
0x180014693  mov     rax, [rax+20h]
0x180014697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001469c  test    eax, eax
0x18001469e  js      short loc_1800146AA
0x1800146a0  mov     rax, [rbp+57h+var_58]
0x1800146a4  mov     [rsi+10h], rax
0x1800146a8  jmp     short loc_18001470D
0x1800146aa  mov     [rbp+57h+hMonitor], 0
0x1800146b2  mov     rcx, [rbp+57h+var_70]
0x1800146b6  mov     rax, [rcx]
0x1800146b9  lea     rdx, [rbp+57h+hMonitor]
0x1800146bd  mov     rax, [rax+18h]
0x1800146c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146c6  test    eax, eax
0x1800146c8  js      short loc_180014711
0x1800146ca  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x1800146d1  xorps   xmm0, xmm0
0x1800146d4  xor     eax, eax
0x1800146d6  movups  xmmword ptr [rbp+57h+mi.rcMonitor.left], xmm0
0x1800146da  movups  xmmword ptr [rbp+57h+mi.rcWork.left], xmm0
0x1800146de  mov     [rbp+57h+mi.dwFlags], eax
0x1800146e1  lea     rdx, [rbp+57h+mi]; lpmi
0x1800146e5  mov     rcx, [rbp+57h+hMonitor]; hMonitor
0x1800146e9  call    cs:__imp_GetMonitorInfoW
0x1800146ef  test    eax, eax
0x1800146f1  jz      short loc_180014711
0x1800146f3  mov     eax, [rbp+57h+mi.rcWork.right]
0x1800146f6  add     eax, [rbp+57h+mi.rcWork.left]
0x1800146f9  cdq
0x1800146fa  idiv    r12d
0x1800146fd  mov     [rsi+10h], eax
0x180014700  mov     eax, [rbp+57h+mi.rcWork.top]
0x180014703  add     eax, [rbp+57h+mi.rcWork.bottom]
0x180014706  cdq
0x180014707  idiv    r12d
0x18001470a  mov     [rsi+14h], eax
0x18001470d  mov     byte ptr [rsi+18h], 1
0x180014711  lea     rcx, [rbp+57h+var_70]
0x180014715  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001471a  nop
0x18001471b  lea     rcx, [rbp+57h+var_60]
0x18001471f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014724  cmp     byte ptr [rsi+18h], 0
0x180014728  jnz     loc_1800147B7
0x18001472e  call    cs:__imp_GetCurrentProcessId
0x180014734  mov     [rbp+57h+hMonitor], 0
0x18001473c  lea     rcx, [rbp+57h+hMonitor]
0x180014740  mov     [rbp+57h+lParam], rcx
0x180014744  mov     [rbp+57h+var_48], eax
0x180014747  lea     rdx, [rbp+57h+lParam]; lParam
0x18001474b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_e1b59a74a951869dc8650816fa791795_@@CAHPEAUHWND__@@_J@Z; lpEnumFunc
0x180014752  call    cs:__imp_EnumWindows
0x180014758  mov     rax, [rbp+57h+hMonitor]
0x18001475c  test    rax, rax
0x18001475f  jnz     short loc_18001476C
0x180014761  lea     edx, [rax+1]; dwFlags
0x180014764  xor     ecx, ecx; hwnd
0x180014766  call    cs:__imp_MonitorFromWindow
0x18001476c  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x180014773  xorps   xmm0, xmm0
0x180014776  xor     ecx, ecx
0x180014778  movups  xmmword ptr [rbp+57h+mi.rcMonitor.left], xmm0
0x18001477c  movups  xmmword ptr [rbp+57h+mi.rcWork.left], xmm0
0x180014780  mov     [rbp+57h+mi.dwFlags], ecx
0x180014783  test    rax, rax
0x180014786  jz      short loc_1800147B7
0x180014788  lea     rdx, [rbp+57h+mi]; lpmi
0x18001478c  mov     rcx, rax; hMonitor
0x18001478f  call    cs:__imp_GetMonitorInfoW
0x180014795  test    eax, eax
0x180014797  jz      short loc_1800147B7
0x180014799  mov     eax, [rbp+57h+mi.rcWork.right]
0x18001479c  add     eax, [rbp+57h+mi.rcWork.left]
0x18001479f  cdq
0x1800147a0  idiv    r12d
0x1800147a3  mov     [rsi+10h], eax
0x1800147a6  mov     eax, [rbp+57h+mi.rcWork.top]
0x1800147a9  add     eax, [rbp+57h+mi.rcWork.bottom]
0x1800147ac  cdq
0x1800147ad  idiv    r12d
0x1800147b0  mov     [rsi+14h], eax
0x1800147b3  mov     byte ptr [rsi+18h], 1
0x1800147b7  mov     rax, rsi
0x1800147ba  mov     rcx, [rbp+57h+var_18]
0x1800147be  xor     rcx, rsp; StackCookie
0x1800147c1  call    __security_check_cookie
0x1800147c6  lea     r11, [rsp+0A0h+var_10]
0x1800147ce  mov     rbx, [r11+28h]
0x1800147d2  mov     rsi, [r11+30h]
0x1800147d6  mov     rsp, r11
0x1800147d9  pop     r12
0x1800147db  pop     rdi
0x1800147dc  pop     rbp
0x1800147dd  retn
```
