# CSdController::Register(ISdCallback2 *,_GUID *)

- ea: `0x18000fda0`
- end: `0x18000ff89`
- name: `?Register@CSdController@@UEAAJPEAUISdCallback2@@PEAU_GUID@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(CSdController *__hidden this, struct IUnknown *, struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000fda0`
- `0x1800138bc`
- `0x18001586c`
- `0x180015974`
- `0x18001a448`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fe6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fe6c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000ff0a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000ff0a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000fecd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000fecd`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000fe41`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000fe41`

## pseudocode

```c
__int64 __fastcall CSdController::Register(CSdController *this, struct IUnknown *a2, struct _GUID *a3)
{
  void *v6; // rcx
  __int64 v7; // rdx
  struct _GUID *v8; // rax
  int v9; // ebx
  __int16 v10; // ax
  bool v11; // zf
  __int16 v12; // ax
  struct _GUID *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rcx
  struct _GUID v17; // [rsp+20h] [rbp-58h] BYREF
  HRESULT Guid; // [rsp+30h] [rbp-48h] BYREF
  __int16 v19; // [rsp+34h] [rbp-44h]
  __int16 v20; // [rsp+36h] [rbp-42h]
  void *ppInterface; // [rsp+B8h] [rbp+40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&Guid, "CSdController::Register", 0xA10u, 1u);
  v6 = 0;
  ppInterface = 0;
  if ( a3 )
  {
    v7 = 16;
    v8 = a3;
    do
    {
      LOBYTE(v8->Data1) = 0;
      v8 = (struct _GUID *)((char *)v8 + 1);
      --v7;
    }
    while ( v7 );
  }
  if ( !a2 )
  {
    v9 = -2147024809;
    v20 = 2582;
    Guid = -2147024809;
    goto LABEL_25;
  }
  Guid = 0;
  v19 = 2582;
  v9 = ConfigureProxySecurityBlanket(a2);
  Guid = v9;
  v10 = 2584;
  if ( v9 < 0 )
    goto LABEL_7;
  v19 = 2584;
  v11 = CoGetCallContext(&IID_ISecurityCallContext, &ppInterface) == -2147467262;
  v10 = 2589;
  if ( v11 )
  {
    Guid = 0;
    v19 = 2589;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    v12 = 2601;
    if ( !*((_DWORD *)this + 27) )
    {
      Guid = -2130706207;
LABEL_12:
      v20 = v12;
LABEL_23:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      v9 = Guid;
      goto LABEL_24;
    }
    v11 = *((_QWORD *)this + 18) == 0;
    v13 = (struct _GUID *)((char *)this + 112);
    Guid = 0;
    v19 = 2601;
    if ( !v11 )
    {
      v17 = *v13;
      Guid = CSdController::_ReleaseUI(this, &v17);
      v12 = 2609;
      if ( Guid < 0 )
        goto LABEL_12;
      v19 = 2609;
      Guid = CoCreateGuid((GUID *)this + 7);
      v12 = 2610;
      if ( Guid < 0 )
        goto LABEL_12;
      v14 = *((_QWORD *)this + 18);
      v19 = 2610;
      if ( v14 )
      {
        *((_QWORD *)this + 18) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    WakeAllConditionVariable((PCONDITION_VARIABLE)this + 6);
    if ( *((struct IUnknown **)this + 18) != a2 )
    {
      ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
      v15 = *((_QWORD *)this + 18);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      *((_QWORD *)this + 18) = a2;
    }
    *a3 = *v13;
    goto LABEL_23;
  }
  v9 = -2147024891;
  Guid = -2147024891;
LABEL_7:
  v20 = v10;
LABEL_24:
  v6 = ppInterface;
LABEL_25:
  if ( v6 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&Guid);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000fda0  push    rbp
0x18000fda2  push    rbx
0x18000fda3  push    rsi
0x18000fda4  push    rdi
0x18000fda5  push    r14
0x18000fda7  push    r15
0x18000fda9  mov     rbp, rsp
0x18000fdac  sub     rsp, 78h
0x18000fdb0  mov     r15, r8
0x18000fdb3  mov     rsi, rdx
0x18000fdb6  mov     rdi, rcx
0x18000fdb9  lea     rdx, aCsdcontrollerR_0; "CSdController::Register"
0x18000fdc0  mov     r8d, 0A10h; unsigned __int16
0x18000fdc6  lea     rcx, [rbp+var_48]; this
0x18000fdca  mov     r9d, 1; unsigned __int16
0x18000fdd0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000fdd5  xor     ecx, ecx
0x18000fdd7  mov     [rbp+ppInterface], rcx
0x18000fddb  test    r15, r15
0x18000fdde  jz      short loc_18000FDF1
0x18000fde0  lea     edx, [rcx+10h]
0x18000fde3  mov     rax, r15
0x18000fde6  mov     [rax], cl
0x18000fde8  inc     rax
0x18000fdeb  sub     rdx, 1
0x18000fdef  jnz     short loc_18000FDE6
0x18000fdf1  mov     eax, 0A16h
0x18000fdf6  test    rsi, rsi
0x18000fdf9  jnz     short loc_18000FE0C
0x18000fdfb  mov     ebx, 80070057h
0x18000fe00  mov     [rbp+var_42], ax
0x18000fe04  mov     [rbp+var_48], ebx
0x18000fe07  jmp     loc_18000FF60
0x18000fe0c  mov     [rbp+var_48], ecx
0x18000fe0f  mov     rcx, rsi; struct IUnknown *
0x18000fe12  mov     [rbp+var_44], ax
0x18000fe16  call    ?ConfigureProxySecurityBlanket@@YAJPEAUIUnknown@@@Z; ConfigureProxySecurityBlanket(IUnknown *)
0x18000fe1b  mov     ebx, eax
0x18000fe1d  mov     [rbp+var_48], eax
0x18000fe20  test    eax, eax
0x18000fe22  mov     eax, 0A18h
0x18000fe27  jns     short loc_18000FE32
0x18000fe29  mov     [rbp+var_42], ax
0x18000fe2d  jmp     loc_18000FF5C
0x18000fe32  lea     rdx, [rbp+ppInterface]; ppInterface
0x18000fe36  mov     [rbp+var_44], ax
0x18000fe3a  lea     rcx, IID_ISecurityCallContext; riid
0x18000fe41  call    cs:__imp_CoGetCallContext
0x18000fe47  cmp     eax, 80004002h
0x18000fe4c  mov     eax, 0A1Dh
0x18000fe51  jz      short loc_18000FE5D
0x18000fe53  mov     ebx, 80070005h
0x18000fe58  mov     [rbp+var_48], ebx
0x18000fe5b  jmp     short loc_18000FE29
0x18000fe5d  lea     rcx, [rdi+40h]; lpCriticalSection
0x18000fe61  mov     [rbp+var_48], 0
0x18000fe68  mov     [rbp+var_44], ax
0x18000fe6c  call    cs:__imp_EnterCriticalSection
0x18000fe72  cmp     dword ptr [rdi+6Ch], 0
0x18000fe76  mov     eax, 0A29h
0x18000fe7b  jnz     short loc_18000FE8D
0x18000fe7d  mov     [rbp+var_48], 810000E1h
0x18000fe84  mov     [rbp+var_42], ax
0x18000fe88  jmp     loc_18000FF4F
0x18000fe8d  cmp     qword ptr [rdi+90h], 0
0x18000fe95  lea     rbx, [rdi+70h]
0x18000fe99  mov     [rbp+var_48], 0
0x18000fea0  mov     [rbp+var_44], ax
0x18000fea4  jz      short loc_18000FF06
0x18000fea6  movups  xmm0, xmmword ptr [rbx]
0x18000fea9  lea     rdx, [rbp+var_58]; struct _GUID
0x18000fead  mov     rcx, rdi; this
0x18000feb0  movdqu  xmmword ptr [rbp+var_58.Data1], xmm0
0x18000feb5  call    ?_ReleaseUI@CSdController@@AEAAJU_GUID@@@Z; CSdController::_ReleaseUI(_GUID)
0x18000feba  mov     [rbp+var_48], eax
0x18000febd  test    eax, eax
0x18000febf  mov     eax, 0A31h
0x18000fec4  js      short loc_18000FE84
0x18000fec6  mov     rcx, rbx; pguid
0x18000fec9  mov     [rbp+var_44], ax
0x18000fecd  call    cs:__imp_CoCreateGuid
0x18000fed3  mov     [rbp+var_48], eax
0x18000fed6  test    eax, eax
0x18000fed8  mov     eax, 0A32h
0x18000fedd  js      short loc_18000FE84
0x18000fedf  mov     rcx, [rdi+90h]
0x18000fee6  mov     [rbp+var_44], ax
0x18000feea  test    rcx, rcx
0x18000feed  jz      short loc_18000FF06
0x18000feef  mov     qword ptr [rdi+90h], 0
0x18000fefa  mov     rax, [rcx]
0x18000fefd  mov     rax, [rax+10h]
0x18000ff01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff06  lea     rcx, [rdi+30h]; ConditionVariable
0x18000ff0a  call    cs:__imp_WakeAllConditionVariable
0x18000ff10  cmp     [rdi+90h], rsi
0x18000ff17  jz      short loc_18000FF47
0x18000ff19  mov     rax, [rsi]
0x18000ff1c  mov     rcx, rsi
0x18000ff1f  mov     rax, [rax+8]
0x18000ff23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff28  mov     rcx, [rdi+90h]
0x18000ff2f  test    rcx, rcx
0x18000ff32  jz      short loc_18000FF40
0x18000ff34  mov     rax, [rcx]
0x18000ff37  mov     rax, [rax+10h]
0x18000ff3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff40  mov     [rdi+90h], rsi
0x18000ff47  movups  xmm0, xmmword ptr [rbx]
0x18000ff4a  movdqu  xmmword ptr [r15], xmm0
0x18000ff4f  lea     rcx, [rdi+40h]; lpCriticalSection
0x18000ff53  call    cs:__imp_LeaveCriticalSection
0x18000ff59  mov     ebx, [rbp+var_48]
0x18000ff5c  mov     rcx, [rbp+ppInterface]
0x18000ff60  test    rcx, rcx
0x18000ff63  jz      short loc_18000FF71
0x18000ff65  mov     rdx, [rcx]
0x18000ff68  mov     rax, [rdx+10h]
0x18000ff6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff71  lea     rcx, [rbp+var_48]; this
0x18000ff75  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ff7a  mov     eax, ebx
0x18000ff7c  add     rsp, 78h
0x18000ff80  pop     r15
0x18000ff82  pop     r14
0x18000ff84  pop     rdi
0x18000ff85  pop     rsi
0x18000ff86  pop     rbx
0x18000ff87  pop     rbp
0x18000ff88  retn
```
