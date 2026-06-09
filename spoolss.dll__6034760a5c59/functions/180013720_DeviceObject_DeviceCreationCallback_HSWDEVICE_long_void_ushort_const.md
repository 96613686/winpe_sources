# DeviceObject::DeviceCreationCallback(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x180013720`
- end: `0x180013867`
- name: `?DeviceCreationCallback@DeviceObject@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `327`
- prototype: `static void(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callees

- `0x180002730`
- `0x180013238`
- `0x180013720`
- `0x180013acc`
- `0x180013b40`
- `0x180013e70`
- `0x180013f00`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013753`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013753`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001377f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800137ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001377f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800137ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013835`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013835`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001375c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001375c`
- `CFGMGR32!SwDeviceSetLifetime` at `0x180013826`
- `CFGMGR32!SwDeviceSetLifetime` at `0x180013826`

## pseudocode

```c
void __fastcall DeviceObject::DeviceCreationCallback(
        struct HSWDEVICE__ *a1,
        int a2,
        DeviceCreationCallbackContext *a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rdi
  char v5; // r15
  int v11; // ebp
  int v12; // eax
  unsigned int v13; // edx
  void (__fastcall *v14)(__int64, _QWORD, _QWORD); // rax
  void *v15; // rcx
  int v16; // [rsp+58h] [rbp+10h] BYREF

  v4 = *(_QWORD *)a3;
  v5 = 0;
  if ( a2 < 0 )
  {
    v11 = a2;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
    ++*(_DWORD *)(v4 + 92);
    *(_DWORD *)(v4 + 88) = GetCurrentThreadId();
    if ( *(_QWORD *)(v4 + 16) )
    {
      if ( (*(_DWORD *)(v4 + 92))-- == 1 )
        *(_DWORD *)(v4 + 88) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
      v11 = -2147020579;
    }
    else
    {
      *(_QWORD *)(v4 + 16) = a1;
      v12 = NCoreLibrary::TString::Update((NCoreLibrary::TString *)(v4 + 40), a4);
      --*(_DWORD *)(v4 + 92);
      v11 = v12;
      if ( !*(_DWORD *)(v4 + 92) )
        *(_DWORD *)(v4 + 88) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
    }
  }
  DeviceObject::OnReady((DeviceObject *)v4, a2);
  if ( v11 >= 0 && (v14 = (void (__fastcall *)(__int64, _QWORD, _QWORD))*((_QWORD *)a3 + 2)) != 0 )
  {
    v14(v4, (unsigned int)a2, *((_QWORD *)a3 + 3));
    v16 = 0;
  }
  else
  {
    v16 = 0;
    if ( v11 < 0 )
      goto LABEL_17;
  }
  if ( (int)GetServerPolicy(L"DemandStartEnabled", &v16) >= 0
    && (int)DeviceObject::MarkObjectInUse((DeviceObject *)v4) >= 0 )
  {
    v5 = 1;
    SwDeviceSetLifetime(a1, v16 != 0);
  }
LABEL_17:
  v15 = (void *)*((_QWORD *)a3 + 1);
  if ( v15 )
    SetEvent(v15);
  if ( v5 )
    DeviceObject::UnmarkObjectInUse((DeviceObject *)v4);
  DeviceCreationCallbackContext::`scalar deleting destructor'(a3, v13);
}

```

## disassembly

```asm
0x180013720  mov     [rsp+arg_0], rbx
0x180013725  mov     [rsp+arg_10], rbp
0x18001372a  push    rsi
0x18001372b  push    rdi
0x18001372c  push    r12
0x18001372e  push    r14
0x180013730  push    r15
0x180013732  sub     rsp, 20h
0x180013736  mov     rdi, [r8]
0x180013739  xor     r15b, r15b
0x18001373c  mov     rbp, r9
0x18001373f  mov     rsi, r8
0x180013742  mov     r14d, edx
0x180013745  mov     r12, rcx
0x180013748  test    edx, edx
0x18001374a  js      short loc_1800137B6
0x18001374c  lea     rbx, [rdi+30h]
0x180013750  mov     rcx, rbx; lpCriticalSection
0x180013753  call    cs:__imp_EnterCriticalSection
0x180013759  inc     dword ptr [rbx+2Ch]
0x18001375c  call    cs:__imp_GetCurrentThreadId
0x180013762  mov     [rbx+28h], eax
0x180013765  cmp     qword ptr [rdi+10h], 0
0x18001376a  jz      short loc_18001378C
0x18001376c  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180013770  mov     eax, [rbx+2Ch]
0x180013773  jnz     short loc_18001377C
0x180013775  mov     dword ptr [rbx+28h], 0
0x18001377c  mov     rcx, rbx; lpCriticalSection
0x18001377f  call    cs:__imp_LeaveCriticalSection
0x180013785  mov     ebp, 800710DDh
0x18001378a  jmp     short loc_1800137B9
0x18001378c  lea     rcx, [rdi+28h]; this
0x180013790  mov     [rdi+10h], r12
0x180013794  mov     rdx, rbp; unsigned __int16 *
0x180013797  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x18001379c  dec     dword ptr [rbx+2Ch]
0x18001379f  mov     ebp, eax
0x1800137a1  mov     ecx, [rbx+2Ch]
0x1800137a4  test    ecx, ecx
0x1800137a6  jnz     short loc_1800137AB
0x1800137a8  mov     [rbx+28h], ecx
0x1800137ab  mov     rcx, rbx; lpCriticalSection
0x1800137ae  call    cs:__imp_LeaveCriticalSection
0x1800137b4  jmp     short loc_1800137B9
0x1800137b6  mov     ebp, r14d
0x1800137b9  mov     edx, r14d; int
0x1800137bc  mov     rcx, rdi; this
0x1800137bf  call    ?OnReady@DeviceObject@@AEAAXJ@Z; DeviceObject::OnReady(long)
0x1800137c4  test    ebp, ebp
0x1800137c6  js      short loc_1800137EA
0x1800137c8  mov     rax, [rsi+10h]
0x1800137cc  test    rax, rax
0x1800137cf  jz      short loc_1800137EA
0x1800137d1  mov     r8, [rsi+18h]
0x1800137d5  mov     edx, r14d
0x1800137d8  mov     rcx, rdi
0x1800137db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137e0  mov     [rsp+48h+arg_8], 0
0x1800137e8  jmp     short loc_1800137F6
0x1800137ea  mov     [rsp+48h+arg_8], 0
0x1800137f2  test    ebp, ebp
0x1800137f4  js      short loc_18001382C
0x1800137f6  lea     rdx, [rsp+48h+arg_8]
0x1800137fb  lea     rcx, aDemandstartena; "DemandStartEnabled"
0x180013802  call    GetServerPolicy
0x180013807  test    eax, eax
0x180013809  js      short loc_18001382C
0x18001380b  mov     rcx, rdi; this
0x18001380e  call    ?MarkObjectInUse@DeviceObject@@IEAAJXZ; DeviceObject::MarkObjectInUse(void)
0x180013813  test    eax, eax
0x180013815  js      short loc_18001382C
0x180013817  xor     edx, edx
0x180013819  mov     rcx, r12
0x18001381c  cmp     [rsp+48h+arg_8], edx
0x180013820  mov     r15b, 1
0x180013823  setnz   dl
0x180013826  call    cs:__imp_SwDeviceSetLifetime
0x18001382c  mov     rcx, [rsi+8]; hEvent
0x180013830  test    rcx, rcx
0x180013833  jz      short loc_18001383B
0x180013835  call    cs:__imp_SetEvent
0x18001383b  test    r15b, r15b
0x18001383e  jz      short loc_180013848
0x180013840  mov     rcx, rdi; this
0x180013843  call    ?UnmarkObjectInUse@DeviceObject@@IEAAXXZ; DeviceObject::UnmarkObjectInUse(void)
0x180013848  mov     rcx, rsi; this
0x18001384b  call    ??_GDeviceCreationCallbackContext@@QEAAPEAXI@Z; DeviceCreationCallbackContext::`scalar deleting destructor'(uint)
0x180013850  mov     rbx, [rsp+48h+arg_0]
0x180013855  mov     rbp, [rsp+48h+arg_10]
0x18001385a  add     rsp, 20h
0x18001385e  pop     r15
0x180013860  pop     r14
0x180013862  pop     r12
0x180013864  pop     rdi
0x180013865  pop     rsi
0x180013866  retn
```
