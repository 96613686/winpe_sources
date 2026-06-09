# CSdController::WaitForCompletion(ulong,_GUID)

- ea: `0x180010540`
- end: `0x18001061a`
- name: `?WaitForCompletion@CSdController@@UEAAJKU_GUID@@@Z`
- size: `218`
- prototype: `int(CSdController *__hidden this, unsigned int, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180010540`
- `0x180013c48`
- `0x18001586c`
- `0x180015974`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800105fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800105fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010575`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010575`

## string_xrefs

- `0x180010551`: `CSdController::WaitForCompletion`

## pseudocode

```c
__int64 __fastcall CSdController::WaitForCompletion(CSdController *this, DWORD a2, struct _GUID *a3)
{
  __int16 v6; // ax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-68h] BYREF
  __int16 v10; // [rsp+24h] [rbp-64h]
  __int16 v11; // [rsp+26h] [rbp-62h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CSdController::WaitForCompletion", 2800, 1);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( !*((_DWORD *)this + 27)
    || *(_QWORD *)&a3->Data1 != *((_QWORD *)this + 14)
    || *(_QWORD *)a3->Data4 != *((_QWORD *)this + 15) )
  {
    v6 = 2814;
    goto LABEL_12;
  }
  v9 = CSdController::_SleepConditionVariable((PCONDITION_VARIABLE)this + 7, (PCRITICAL_SECTION)((char *)this + 64), a2);
  if ( v9 >= 0 )
  {
    if ( *((_DWORD *)this + 27)
      && *(_QWORD *)&a3->Data1 == *((_QWORD *)this + 14)
      && *(_QWORD *)a3->Data4 == *((_QWORD *)this + 15) )
    {
      v9 = 1;
      v6 = 2824;
LABEL_13:
      v10 = v6;
      goto LABEL_14;
    }
    v6 = 2821;
LABEL_12:
    v9 = 0;
    goto LABEL_13;
  }
  v11 = 2817;
LABEL_14:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v7 = v9;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v7;
}

```

## disassembly

```asm
0x180010540  push    rbx
0x180010542  push    rbp
0x180010543  push    rsi
0x180010544  push    rdi
0x180010545  sub     rsp, 68h
0x180010549  mov     rdi, r8
0x18001054c  mov     ebp, edx
0x18001054e  mov     rbx, rcx
0x180010551  lea     rdx, aCsdcontrollerW_0; "CSdController::WaitForCompletion"
0x180010558  mov     r8d, 0AF0h; unsigned __int16
0x18001055e  lea     rcx, [rsp+88h+var_68]; this
0x180010563  mov     r9d, 1; unsigned __int16
0x180010569  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001056e  lea     rsi, [rbx+40h]
0x180010572  mov     rcx, rsi; lpCriticalSection
0x180010575  call    cs:__imp_EnterCriticalSection
0x18001057b  cmp     dword ptr [rbx+6Ch], 0
0x18001057f  jz      short loc_1800105E6
0x180010581  mov     rax, [rdi]
0x180010584  cmp     rax, [rbx+70h]
0x180010588  jnz     short loc_1800105E6
0x18001058a  mov     rax, [rdi+8]
0x18001058e  cmp     rax, [rbx+78h]
0x180010592  jnz     short loc_1800105E6
0x180010594  lea     rcx, [rbx+38h]; ConditionVariable
0x180010598  mov     r8d, ebp; dwMilliseconds
0x18001059b  mov     rdx, rsi; CriticalSection
0x18001059e  call    ?_SleepConditionVariable@CSdController@@CAJPEAU_RTL_CONDITION_VARIABLE@@PEAU_RTL_CRITICAL_SECTION@@K@Z; CSdController::_SleepConditionVariable(_RTL_CONDITION_VARIABLE *,_RTL_CRITICAL_SECTION *,ulong)
0x1800105a3  mov     [rsp+88h+var_68], eax
0x1800105a7  test    eax, eax
0x1800105a9  jns     short loc_1800105B7
0x1800105ab  mov     eax, 0B01h
0x1800105b0  mov     [rsp+88h+var_62], ax
0x1800105b5  jmp     short loc_1800105F8
0x1800105b7  cmp     dword ptr [rbx+6Ch], 0
0x1800105bb  jz      short loc_1800105DF
0x1800105bd  mov     rax, [rdi]
0x1800105c0  cmp     rax, [rbx+70h]
0x1800105c4  jnz     short loc_1800105DF
0x1800105c6  mov     rax, [rdi+8]
0x1800105ca  cmp     rax, [rbx+78h]
0x1800105ce  jnz     short loc_1800105DF
0x1800105d0  mov     [rsp+88h+var_68], 1
0x1800105d8  mov     eax, 0B08h
0x1800105dd  jmp     short loc_1800105F3
0x1800105df  mov     eax, 0B05h
0x1800105e4  jmp     short loc_1800105EB
0x1800105e6  mov     eax, 0AFEh
0x1800105eb  mov     [rsp+88h+var_68], 0
0x1800105f3  mov     [rsp+88h+var_64], ax
0x1800105f8  mov     rcx, rsi; lpCriticalSection
0x1800105fb  call    cs:__imp_LeaveCriticalSection
0x180010601  mov     ebx, [rsp+88h+var_68]
0x180010605  lea     rcx, [rsp+88h+var_68]; this
0x18001060a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001060f  mov     eax, ebx
0x180010611  add     rsp, 68h
0x180010615  pop     rdi
0x180010616  pop     rsi
0x180010617  pop     rbp
0x180010618  pop     rbx
0x180010619  retn
```
