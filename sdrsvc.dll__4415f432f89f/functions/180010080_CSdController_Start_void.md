# CSdController::Start(void)

- ea: `0x180010080`
- end: `0x1800101b7`
- name: `?Start@CSdController@@UEAAJXZ`
- size: `311`
- prototype: `__int64 __fastcall(CSdController *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010080`
- `0x180012948`
- `0x18001586c`
- `0x180015974`
- `0x180017e90`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001012d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001016a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001012d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001016a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001010e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001010e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180010161`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180010161`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800100ef`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800100ef`

## pseudocode

```c
__int64 __fastcall CSdController::Start(CSdController *this)
{
  HRESULT v2; // ebx
  __int16 v3; // ax
  int v5; // [rsp+20h] [rbp-50h] BYREF
  __int16 v6; // [rsp+24h] [rbp-4Ch]
  __int16 v7; // [rsp+26h] [rbp-4Ah]
  GUID pguid; // [rsp+58h] [rbp-18h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v5, "CSdController::Start", 0xB81u, 1u);
  pguid = GUID_NULL;
  v2 = VerifyCallerSystem();
  v5 = v2;
  v3 = 2954;
  if ( v2 >= 0 )
  {
    v6 = 2954;
    v2 = CoCreateGuid(&pguid);
    v5 = v2;
    v3 = 2961;
    if ( v2 >= 0 )
    {
      v6 = 2961;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      if ( *((_DWORD *)this + 27) )
      {
        v5 = -2130706206;
        v7 = 2972;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        v2 = v5;
        goto LABEL_8;
      }
      v5 = 0;
      v6 = 2972;
      *((GUID *)this + 7) = pguid;
      *((_DWORD *)this + 27) = 1;
      *((_DWORD *)this + 32) = 0;
      WakeAllConditionVariable((PCONDITION_VARIABLE)this + 7);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      v2 = CSdController::_PerformScheduledBackup(this);
      v5 = v2;
      v3 = 2991;
      if ( v2 >= 0 )
      {
        v6 = 2991;
        goto LABEL_8;
      }
    }
  }
  v7 = v3;
LABEL_8:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v5);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180010080  mov     [rsp-8+arg_8], rbx
0x180010085  mov     [rsp-8+arg_10], rdi
0x18001008a  push    rbp
0x18001008b  mov     rbp, rsp
0x18001008e  sub     rsp, 70h
0x180010092  mov     rax, cs:__security_cookie
0x180010099  xor     rax, rsp
0x18001009c  mov     [rbp+var_8], rax
0x1800100a0  mov     rdi, rcx
0x1800100a3  lea     rdx, aCsdcontrollerS_1; "CSdController::Start"
0x1800100aa  lea     rcx, [rbp+var_50]; this
0x1800100ae  mov     r9d, 1; unsigned __int16
0x1800100b4  mov     r8d, 0B81h; unsigned __int16
0x1800100ba  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800100bf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800100c6  movdqu  xmmword ptr [rbp+pguid.Data1], xmm0
0x1800100cb  call    ?VerifyCallerSystem@@YAJXZ; VerifyCallerSystem(void)
0x1800100d0  mov     ebx, eax
0x1800100d2  mov     [rbp+var_50], eax
0x1800100d5  test    eax, eax
0x1800100d7  mov     eax, 0B8Ah
0x1800100dc  jns     short loc_1800100E7
0x1800100de  mov     [rbp+var_4A], ax
0x1800100e2  jmp     loc_18001018E
0x1800100e7  lea     rcx, [rbp+pguid]; pguid
0x1800100eb  mov     [rbp+var_4C], ax
0x1800100ef  call    cs:__imp_CoCreateGuid
0x1800100f5  mov     ebx, eax
0x1800100f7  mov     [rbp+var_50], eax
0x1800100fa  test    eax, eax
0x1800100fc  mov     eax, 0B91h
0x180010101  js      short loc_1800100DE
0x180010103  lea     rbx, [rdi+40h]
0x180010107  mov     [rbp+var_4C], ax
0x18001010b  mov     rcx, rbx; lpCriticalSection
0x18001010e  call    cs:__imp_EnterCriticalSection
0x180010114  cmp     dword ptr [rdi+6Ch], 0
0x180010118  mov     eax, 0B9Ch
0x18001011d  jz      short loc_180010138
0x18001011f  mov     rcx, rbx; lpCriticalSection
0x180010122  mov     [rbp+var_50], 810000E2h
0x180010129  mov     [rbp+var_4A], ax
0x18001012d  call    cs:__imp_LeaveCriticalSection
0x180010133  mov     ebx, [rbp+var_50]
0x180010136  jmp     short loc_18001018E
0x180010138  movups  xmm0, xmmword ptr [rbp+pguid.Data1]
0x18001013c  lea     rcx, [rdi+38h]; ConditionVariable
0x180010140  mov     [rbp+var_50], 0
0x180010147  mov     [rbp+var_4C], ax
0x18001014b  movdqu  xmmword ptr [rdi+70h], xmm0
0x180010150  mov     dword ptr [rdi+6Ch], 1
0x180010157  mov     dword ptr [rdi+80h], 0
0x180010161  call    cs:__imp_WakeAllConditionVariable
0x180010167  mov     rcx, rbx; lpCriticalSection
0x18001016a  call    cs:__imp_LeaveCriticalSection
0x180010170  mov     rcx, rdi; this
0x180010173  call    ?_PerformScheduledBackup@CSdController@@AEAAJXZ; CSdController::_PerformScheduledBackup(void)
0x180010178  mov     ebx, eax
0x18001017a  mov     [rbp+var_50], eax
0x18001017d  test    eax, eax
0x18001017f  mov     eax, 0BAFh
0x180010184  js      loc_1800100DE
0x18001018a  mov     [rbp+var_4C], ax
0x18001018e  lea     rcx, [rbp+var_50]; this
0x180010192  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180010197  mov     eax, ebx
0x180010199  mov     rcx, [rbp+var_8]
0x18001019d  xor     rcx, rsp; StackCookie
0x1800101a0  call    __security_check_cookie
0x1800101a5  lea     r11, [rsp+70h+var_s0]
0x1800101aa  mov     rbx, [r11+18h]
0x1800101ae  mov     rdi, [r11+20h]
0x1800101b2  mov     rsp, r11
0x1800101b5  pop     rbp
0x1800101b6  retn
```
