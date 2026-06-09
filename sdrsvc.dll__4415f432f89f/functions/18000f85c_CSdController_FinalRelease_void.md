# CSdController::FinalRelease(void)

- ea: `0x18000f85c`
- end: `0x18000f8be`
- name: `?FinalRelease@CSdController@@AEAAXXZ`
- size: `98`
- prototype: `void __fastcall(CSdController *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180008a40`
- `0x180008c00`
- `0x180008ce0`
- `0x18000a7a8`
- `0x18000cc80`

## callees

- `0x18000f85c`
- `0x1800138bc`
- `0x18001586c`
- `0x180015974`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f8a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f8a1`

## pseudocode

```c
void __fastcall CSdController::FinalRelease(CSdController *this)
{
  struct _GUID v2; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v3[72]; // [rsp+30h] [rbp-48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v3, "CSdController::FinalRelease", 71, 1);
  v2 = (struct _GUID)*((_OWORD *)this + 7);
  CSdController::_ReleaseUI(this, &v2);
  if ( *((_DWORD *)this + 26) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    *((_DWORD *)this + 26) = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v3);
}

```

## disassembly

```asm
0x18000f85c  push    rbx
0x18000f85e  sub     rsp, 70h
0x18000f862  mov     r9d, 1; unsigned __int16
0x18000f868  lea     rdx, aCsdcontrollerF_0; "CSdController::FinalRelease"
0x18000f86f  mov     rbx, rcx
0x18000f872  lea     rcx, [rsp+78h+var_48]; this
0x18000f877  lea     r8d, [r9+46h]; unsigned __int16
0x18000f87b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000f880  movups  xmm0, xmmword ptr [rbx+70h]
0x18000f884  lea     rdx, [rsp+78h+var_58]; struct _GUID
0x18000f889  mov     rcx, rbx; this
0x18000f88c  movdqu  xmmword ptr [rsp+78h+var_58.Data1], xmm0
0x18000f892  call    ?_ReleaseUI@CSdController@@AEAAJU_GUID@@@Z; CSdController::_ReleaseUI(_GUID)
0x18000f897  cmp     dword ptr [rbx+68h], 0
0x18000f89b  jz      short loc_18000F8AE
0x18000f89d  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000f8a1  call    cs:__imp_DeleteCriticalSection
0x18000f8a7  mov     dword ptr [rbx+68h], 0
0x18000f8ae  lea     rcx, [rsp+78h+var_48]; this
0x18000f8b3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000f8b8  add     rsp, 70h
0x18000f8bc  pop     rbx
0x18000f8bd  retn
```
