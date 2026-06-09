# CDateTimeOm::Initialize(int,int)

- ea: `0x18001b95c`
- end: `0x18001bb15`
- name: `?Initialize@CDateTimeOm@@QEAAJHH@Z`
- size: `441`
- prototype: `__int64 __fastcall(CDateTimeOm *__hidden this, int, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800075ec`
- `0x180014b24`
- `0x18001a848`
- `0x18001de28`

## callees

- `0x180001dfc`
- `0x180017c50`
- `0x18001b368`
- `0x18001b930`
- `0x18001b95c`
- `0x18001c300`
- `0x18001c560`
- `0x18001c664`
- `0x180028f2e`

## import_xrefs

- `SHLWAPI!SHRegGetValueW` at `0x18001bae7`
- `SHLWAPI!SHRegGetValueW` at `0x18001bae7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ba02`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ba02`
- `USER32!SetTimer` at `0x18001ba56`
- `USER32!SetTimer` at `0x18001ba56`

## pseudocode

```c
__int64 __fastcall CDateTimeOm::Initialize(CDateTimeOm *this, int a2, int a3)
{
  LPVOID *v3; // rbx
  HRESULT Instance; // ebx
  HWND v8; // rdx
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  CDateTimeOm::INTERNET_TIME_OM *v11; // rax
  __int64 v12; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-48h]
  int pvData; // [rsp+70h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+20h] BYREF

  v3 = (LPVOID *)((char *)this + 112);
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_DWORD *)this + 119) = 0;
  *((_DWORD *)this + 107) = 1;
  *((_DWORD *)this + 120) = 1;
  *((_DWORD *)this + 114) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 14) = 0;
  memset_0((char *)this + 172, 0, 0x100u);
  *((_DWORD *)this + 109) = 1;
  *(_OWORD *)((char *)this + 156) = 0;
  *(_OWORD *)((char *)this + 460) = 0;
  *((_QWORD *)this + 61) = 0;
  Instance = CoCreateInstance(&CLSID_DateTimeState, 0, 1u, &GUID_500dd1a1_b32a_4a37_9283_1185fb613899, v3);
  if ( Instance >= 0 )
  {
    GetDateLimits(1u, (struct _SYSTEMTIME *)((char *)this + 140), (struct _SYSTEMTIME *)((char *)this + 124));
    CDateTimeOm::_PollTime(this);
    CDateTimeOm::_UpdateTimeZone(this);
    if ( a2 )
    {
      Instance = CImpWorkerWndProc::HrCreateWorkerWindow(this, v8, v9, v10, (HMENU)ppv);
      if ( Instance >= 0 )
        SetTimer(*((HWND *)this + 1), 0, 0xFAu, 0);
    }
    if ( a3 )
    {
      v11 = (CDateTimeOm::INTERNET_TIME_OM *)operator new(0x438u);
      if ( v11 )
      {
        v12 = CDateTimeOm::INTERNET_TIME_OM::INTERNET_TIME_OM(v11);
        *((_QWORD *)this + 61) = v12;
        if ( v12 )
          Instance = CDateTimeOm::_InitializeInternetTimeOm(this, 1);
      }
      else
      {
        *((_QWORD *)this + 61) = 0;
      }
    }
    pvData = 0;
    pcbData = 4;
    *((_DWORD *)this + 108) = 1;
    if ( !SHRegGetValueW(HKEY_CURRENT_USER, L"Control Panel\\TimeDate", L"DstNotification", 16, 0, &pvData, &pcbData) )
      *((_DWORD *)this + 108) = pvData != 0;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001b95c  mov     [rsp+arg_8], rbx
0x18001b961  push    rbp
0x18001b962  push    rsi
0x18001b963  push    rdi
0x18001b964  push    r14
0x18001b966  push    r15
0x18001b968  sub     rsp, 40h
0x18001b96c  xor     r14d, r14d
0x18001b96f  lea     rbx, [rcx+70h]
0x18001b973  mov     esi, r8d
0x18001b976  mov     [rcx+68h], r14d
0x18001b97a  mov     ebp, edx
0x18001b97c  mov     [rcx+1B8h], r14
0x18001b983  mov     rdi, rcx
0x18001b986  mov     [rcx+1C0h], r14
0x18001b98d  lea     r15d, [r14+1]
0x18001b991  mov     [rcx+1DCh], r14d
0x18001b998  mov     [rcx+1ACh], r15d
0x18001b99f  xor     edx, edx; Val
0x18001b9a1  mov     [rcx+1E0h], r15d
0x18001b9a8  mov     r8d, 100h; Size
0x18001b9ae  mov     [rcx+1C8h], r14d
0x18001b9b5  mov     [rcx+8], r14
0x18001b9b9  add     rcx, 0ACh; void *
0x18001b9c0  mov     [rbx], r14
0x18001b9c3  call    memset_0
0x18001b9c8  mov     [rdi+1B4h], r15d
0x18001b9cf  lea     r9, _GUID_500dd1a1_b32a_4a37_9283_1185fb613899; riid
0x18001b9d6  xorps   xmm0, xmm0
0x18001b9d9  mov     [rsp+68h+ppv], rbx; HMENU
0x18001b9de  movups  xmmword ptr [rdi+9Ch], xmm0
0x18001b9e5  lea     rcx, CLSID_DateTimeState; rclsid
0x18001b9ec  mov     r8d, r15d; dwClsContext
0x18001b9ef  xorps   xmm1, xmm1
0x18001b9f2  xor     edx, edx; pUnkOuter
0x18001b9f4  movups  xmmword ptr [rdi+1CCh], xmm1
0x18001b9fb  mov     [rdi+1E8h], r14
0x18001ba02  call    cs:__imp_CoCreateInstance
0x18001ba08  mov     ebx, eax
0x18001ba0a  test    eax, eax
0x18001ba0c  js      loc_18001BB02
0x18001ba12  lea     r8, [rdi+7Ch]; struct _SYSTEMTIME *
0x18001ba16  mov     ecx, r15d; unsigned int
0x18001ba19  lea     rdx, [rdi+8Ch]; struct _SYSTEMTIME *
0x18001ba20  call    ?GetDateLimits@@YAHIPEAU_SYSTEMTIME@@0@Z; GetDateLimits(uint,_SYSTEMTIME *,_SYSTEMTIME *)
0x18001ba25  mov     rcx, rdi; this
0x18001ba28  call    ?_PollTime@CDateTimeOm@@AEAAXXZ; CDateTimeOm::_PollTime(void)
0x18001ba2d  mov     rcx, rdi; this
0x18001ba30  call    ?_UpdateTimeZone@CDateTimeOm@@AEAAXXZ; CDateTimeOm::_UpdateTimeZone(void)
0x18001ba35  test    ebp, ebp
0x18001ba37  jz      short loc_18001BA5C
0x18001ba39  mov     rcx, rdi; this
0x18001ba3c  call    ?HrCreateWorkerWindow@CImpWorkerWndProc@@IEAAJPEAUHWND__@@KKPEAUHMENU__@@@Z; CImpWorkerWndProc::HrCreateWorkerWindow(HWND__ *,ulong,ulong,HMENU__ *)
0x18001ba41  mov     ebx, eax
0x18001ba43  test    eax, eax
0x18001ba45  js      short loc_18001BA5C
0x18001ba47  mov     rcx, [rdi+8]; hWnd
0x18001ba4b  xor     r9d, r9d; lpTimerFunc
0x18001ba4e  xor     edx, edx; nIDEvent
0x18001ba50  mov     r8d, 0FAh; uElapse
0x18001ba56  call    cs:__imp_SetTimer
0x18001ba5c  test    esi, esi
0x18001ba5e  jz      short loc_18001BA99
0x18001ba60  mov     ecx, 438h; Size
0x18001ba65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ba6a  test    rax, rax
0x18001ba6d  jz      short loc_18001BA92
0x18001ba6f  mov     rcx, rax; this
0x18001ba72  call    ??0INTERNET_TIME_OM@CDateTimeOm@@QEAA@XZ; CDateTimeOm::INTERNET_TIME_OM::INTERNET_TIME_OM(void)
0x18001ba77  mov     [rdi+1E8h], rax
0x18001ba7e  test    rax, rax
0x18001ba81  jz      short loc_18001BA99
0x18001ba83  mov     edx, r15d; int
0x18001ba86  mov     rcx, rdi; this
0x18001ba89  call    ?_InitializeInternetTimeOm@CDateTimeOm@@AEAAJH@Z; CDateTimeOm::_InitializeInternetTimeOm(int)
0x18001ba8e  mov     ebx, eax
0x18001ba90  jmp     short loc_18001BA99
0x18001ba92  mov     [rdi+1E8h], r14
0x18001ba99  lea     rax, [rsp+68h+arg_18]
0x18001baa1  mov     [rsp+68h+arg_0], r14d
0x18001baa6  mov     [rsp+68h+pcbData], rax; pcbData
0x18001baab  lea     r8, Value; "DstNotification"
0x18001bab2  lea     rax, [rsp+68h+arg_0]
0x18001bab7  mov     [rsp+68h+arg_18], 4
0x18001bac2  mov     [rsp+68h+pvData], rax; pvData
0x18001bac7  lea     rdx, SubKey; "Control Panel\\TimeDate"
0x18001bace  mov     r9d, 10h; srrfFlags
0x18001bad4  mov     [rsp+68h+ppv], r14; pdwType
0x18001bad9  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001bae0  mov     [rdi+1B0h], r15d
0x18001bae7  call    cs:__imp_SHRegGetValueW
0x18001baed  test    eax, eax
0x18001baef  jnz     short loc_18001BB02
0x18001baf1  cmp     [rsp+68h+arg_0], r14d
0x18001baf6  mov     eax, r14d
0x18001baf9  setnz   al
0x18001bafc  mov     [rdi+1B0h], eax
0x18001bb02  mov     eax, ebx
0x18001bb04  mov     rbx, [rsp+68h+arg_8]
0x18001bb09  add     rsp, 40h
0x18001bb0d  pop     r15
0x18001bb0f  pop     r14
0x18001bb11  pop     rdi
0x18001bb12  pop     rsi
0x18001bb13  pop     rbp
0x18001bb14  retn
```
