# UWFUpdateAgent::Initialize(void)

- ea: `0x180003c6c`
- end: `0x180003d5f`
- name: `?Initialize@UWFUpdateAgent@@QEAAJXZ`
- size: `243`
- prototype: `__int64 __fastcall(UWFUpdateAgent *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180003260`

## callees

- `0x180002548`
- `0x180002a20`
- `0x180003c6c`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003c9d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003c9d`

## string_xrefs

- `0x180003ca9`: `Failed to create an IUpdateSession`
- `0x180003cee`: `Failed to allocate UpdateStatus`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::Initialize(UWFUpdateAgent *this)
{
  UWFUpdateAgent *v1; // rdi
  _QWORD *v2; // rsi
  HRESULT Instance; // eax
  unsigned int v4; // ebx
  _OWORD *v5; // rax
  __int64 result; // rax

  v1 = qword_18000C840;
  v2 = (_QWORD *)((char *)qword_18000C840 + 8);
  Instance = CoCreateInstance(&CLSID_UpdateSession, 0, 1u, &IID_IUpdateSession, (LPVOID *)qword_18000C840 + 1);
  v4 = Instance;
  if ( Instance >= 0 )
  {
    v5 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)v1 + 2) = v5;
    if ( !v5 )
    {
      UwfServicingLog(1, 1, v4, L"Failed to allocate UpdateStatus");
      UwfServicingLog(1, 1, v4, L"Initialize failed");
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
      result = 2147942414LL;
      *v2 = 0;
      return result;
    }
    *v5 = 0;
    v5[1] = 0;
    *((_QWORD *)v5 + 4) = 0;
    UwfServicingLog(1, 0, 0, L"Initialize sucess");
  }
  else
  {
    UwfServicingLog(1, 1, (unsigned int)Instance, L"Failed to create an IUpdateSession");
    UwfServicingLog(1, 1, v4, L"Initialize failed");
  }
  return v4;
}

```

## disassembly

```asm
0x180003c6c  push    rbx
0x180003c6e  push    rbp
0x180003c6f  push    rsi
0x180003c70  push    rdi
0x180003c71  sub     rsp, 38h
0x180003c75  mov     rdi, cs:qword_18000C840
0x180003c7c  lea     r9, IID_IUpdateSession; riid
0x180003c83  mov     ebp, 1
0x180003c88  lea     rcx, CLSID_UpdateSession; rclsid
0x180003c8f  mov     r8d, ebp; dwClsContext
0x180003c92  xor     edx, edx; pUnkOuter
0x180003c94  lea     rsi, [rdi+8]
0x180003c98  mov     [rsp+58h+ppv], rsi; ppv
0x180003c9d  call    cs:__imp_CoCreateInstance
0x180003ca3  mov     ebx, eax
0x180003ca5  test    eax, eax
0x180003ca7  jns     short loc_180003CD4
0x180003ca9  lea     r9, aFailedToCreate; "Failed to create an IUpdateSession"
0x180003cb0  mov     r8d, eax
0x180003cb3  mov     edx, ebp
0x180003cb5  mov     ecx, ebp
0x180003cb7  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003cbc  lea     r9, aInitializeFail; "Initialize failed"
0x180003cc3  mov     r8d, ebx
0x180003cc6  mov     edx, ebp
0x180003cc8  mov     ecx, ebp
0x180003cca  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003ccf  jmp     loc_180003D54
0x180003cd4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003cdb  mov     ecx, 28h ; '('; unsigned __int64
0x180003ce0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003ce5  mov     [rdi+10h], rax
0x180003ce9  test    rax, rax
0x180003cec  jnz     short loc_180003D31
0x180003cee  lea     r9, aFailedToAlloca; "Failed to allocate UpdateStatus"
0x180003cf5  mov     r8d, ebx
0x180003cf8  mov     edx, ebp
0x180003cfa  mov     ecx, ebp
0x180003cfc  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003d01  lea     r9, aInitializeFail; "Initialize failed"
0x180003d08  mov     r8d, ebx
0x180003d0b  mov     edx, ebp
0x180003d0d  mov     ecx, ebp
0x180003d0f  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003d14  mov     rcx, [rsi]
0x180003d17  mov     rax, [rcx]
0x180003d1a  mov     rax, [rax+10h]
0x180003d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d23  mov     eax, 8007000Eh
0x180003d28  mov     qword ptr [rsi], 0
0x180003d2f  jmp     short loc_180003D56
0x180003d31  xorps   xmm0, xmm0
0x180003d34  lea     r9, aInitializeSuce; "Initialize sucess"
0x180003d3b  movups  xmmword ptr [rax], xmm0
0x180003d3e  xor     ecx, ecx
0x180003d40  xor     r8d, r8d
0x180003d43  movups  xmmword ptr [rax+10h], xmm0
0x180003d47  mov     [rax+20h], rcx
0x180003d4b  xor     edx, edx
0x180003d4d  mov     ecx, ebp
0x180003d4f  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003d54  mov     eax, ebx
0x180003d56  add     rsp, 38h
0x180003d5a  pop     rdi
0x180003d5b  pop     rsi
0x180003d5c  pop     rbp
0x180003d5d  pop     rbx
0x180003d5e  retn
```
