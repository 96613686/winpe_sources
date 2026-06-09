# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002130`
- end: `0x180002234`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180002130`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002165`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002165`
- `iisutil!PuCreateDebugPrintsObject` at `0x18000214c`
- `iisutil!PuCreateDebugPrintsObject` at `0x18000214c`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180002191`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180002191`
- `iisutil!IISGetPlatformType` at `0x18000219d`
- `iisutil!IISGetPlatformType` at `0x18000219d`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180002213`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180002213`

## string_xrefs

- `0x18000215e`: `Unable to Create Debug Print Object \n`
- `0x18000218a`: `System\CurrentControlSet\Services\w3svc\Parameters\urlauthz`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 DebugPrintsObject; // rax
  __int64 v6; // rax
  _QWORD *v7; // rax
  int v8; // ebx

  DebugPrintsObject = PuCreateDebugPrintsObject("urlauthz", 1);
  g_pDebug = DebugPrintsObject;
  if ( DebugPrintsObject
    || (OutputDebugStringA("Unable to Create Debug Print Object \n"), (DebugPrintsObject = g_pDebug) != 0) )
  {
    if ( *(_DWORD *)(DebugPrintsObject + 640) )
    {
      g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\w3svc\\Parameters\\urlauthz", 0);
      IISGetPlatformType();
      v6 = *(_QWORD *)a2;
      g_pGlobalInfo = a3;
      g_UrlAuthzModuleId = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(v6 + 8))(a2);
      v7 = operator new(0x10u);
      if ( v7 )
      {
        *v7 = &CIISModuleFactory::`vftable';
        v7[1] = &CIISHttpModule::`vftable';
        v8 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 16LL))(
               a2,
               v7,
               4);
        if ( v8 >= 0 )
          return 0;
      }
      else
      {
        v8 = -2147024888;
      }
      g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
      return (unsigned int)v8;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180002130  mov     [rsp+arg_0], rbx
0x180002135  push    rdi
0x180002136  sub     rsp, 30h
0x18000213a  mov     rbx, rdx
0x18000213d  lea     rcx, aUrlauthz; "urlauthz"
0x180002144  mov     edx, 1
0x180002149  mov     rdi, r8
0x18000214c  call    cs:__imp_PuCreateDebugPrintsObject
0x180002152  mov     cs:g_pDebug, rax
0x180002159  test    rax, rax
0x18000215c  jnz     short loc_18000217B
0x18000215e  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180002165  call    cs:__imp_OutputDebugStringA
0x18000216b  mov     rax, cs:g_pDebug
0x180002172  test    rax, rax
0x180002175  jz      loc_180002224
0x18000217b  cmp     dword ptr [rax+280h], 0
0x180002182  jz      loc_180002224
0x180002188  xor     edx, edx
0x18000218a  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\w3"...
0x180002191  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180002197  mov     cs:g_dwDebugFlags, eax
0x18000219d  call    cs:__imp_IISGetPlatformType
0x1800021a3  mov     rax, [rbx]
0x1800021a6  mov     rcx, rbx
0x1800021a9  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rdi; IHttpServer * g_pGlobalInfo
0x1800021b0  mov     rax, [rax+8]
0x1800021b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021b9  mov     ecx, 10h; Size
0x1800021be  mov     cs:?g_UrlAuthzModuleId@@3PEAXEA, rax; void * g_UrlAuthzModuleId
0x1800021c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021ca  mov     rdx, rax
0x1800021cd  test    rax, rax
0x1800021d0  jz      short loc_180002207
0x1800021d2  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800021d9  xor     r9d, r9d
0x1800021dc  mov     [rdx], rax
0x1800021df  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x1800021e6  mov     [rdx+8], rax
0x1800021ea  mov     rcx, [rbx]
0x1800021ed  lea     r8d, [r9+4]
0x1800021f1  mov     rax, [rcx+10h]
0x1800021f5  mov     rcx, rbx
0x1800021f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021fd  mov     ebx, eax
0x1800021ff  test    eax, eax
0x180002201  js      short loc_18000220C
0x180002203  xor     ebx, ebx
0x180002205  jmp     short loc_180002220
0x180002207  mov     ebx, 80070008h
0x18000220c  mov     rcx, cs:g_pDebug
0x180002213  call    cs:__imp_PuDeleteDebugPrintsObject
0x180002219  mov     cs:g_pDebug, rax
0x180002220  mov     eax, ebx
0x180002222  jmp     short loc_180002229
0x180002224  mov     eax, 80004005h
0x180002229  mov     rbx, [rsp+38h+arg_0]
0x18000222e  add     rsp, 30h
0x180002232  pop     rdi
0x180002233  retn
```
