# AutoClearCallerClientId::~AutoClearCallerClientId(void)

- ea: `0x180025aa4`
- end: `0x180025b3f`
- name: `??1AutoClearCallerClientId@@QEAA@XZ`
- size: `155`
- prototype: `void __fastcall(AutoClearCallerClientId *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180025520`
- `0x180025720`
- `0x180063e20`
- `0x180066920`
- `0x180066fb0`
- `0x180067e10`
- `0x1800692a8`

## callees

- `0x1800068f0`
- `0x180025aa4`
- `0x180025d68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180025b09`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180025b09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025afe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025afe`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x180025b1d`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x180025b1d`

## string_xrefs

- `0x180025ae2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`

## pseudocode

```c
void __fastcall AutoClearCallerClientId::~AutoClearCallerClientId(unsigned __int64 **this)
{
  int v2; // eax
  int v3; // ebx
  HANDLE CurrentThread; // rax
  enum _PRIORITY_HINT v5; // ecx
  int v6; // eax

  if ( *(_DWORD *)this )
  {
    v2 = SetCallerClientId(0, this + 1);
    if ( v2 < 0 )
      Log_UnistoreHREvent_0(
        (unsigned int)v2,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
        34);
  }
  if ( *((_DWORD *)this + 9) )
  {
    v3 = *((_DWORD *)this + 8);
    *((_DWORD *)this + 9) = 0;
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v3);
  }
  if ( *((_DWORD *)this + 7) )
  {
    v5 = *((_DWORD *)this + 6);
    *((_DWORD *)this + 7) = 0;
    v6 = SetThreadIOPriority(v5, 0);
    if ( v6 < 0 )
      Log_UnistoreHREvent_0((unsigned int)v6, 0, "onecoreuap\\private\\base\\inc\\UserDataPlatformHelper.h", 731);
  }
}

```

## disassembly

```asm
0x180025aa4  mov     [rsp+arg_0], rbx
0x180025aa9  push    rdi
0x180025aaa  sub     rsp, 30h
0x180025aae  cmp     dword ptr [rcx], 0
0x180025ab1  mov     rdi, rcx
0x180025ab4  jnz     short loc_180025ACD
0x180025ab6  cmp     dword ptr [rdi+24h], 0
0x180025aba  jnz     short loc_180025AF4
0x180025abc  cmp     dword ptr [rdi+1Ch], 0
0x180025ac0  jnz     short loc_180025B11
0x180025ac2  mov     rbx, [rsp+38h+arg_0]
0x180025ac7  add     rsp, 30h
0x180025acb  pop     rdi
0x180025acc  retn
0x180025acd  lea     rdx, [rcx+8]; unsigned __int64 **
0x180025ad1  xor     ecx, ecx; lpTlsValue
0x180025ad3  call    ?SetCallerClientId@@YAJPEB_KPEAPEA_K@Z; SetCallerClientId(unsigned __int64 const *,unsigned __int64 * *)
0x180025ad8  test    eax, eax
0x180025ada  jns     short loc_180025AB6
0x180025adc  mov     r9d, 22h ; '"'
0x180025ae2  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180025ae9  xor     edx, edx
0x180025aeb  mov     ecx, eax
0x180025aed  call    Log_UnistoreHREvent_0
0x180025af2  jmp     short loc_180025AB6
0x180025af4  mov     ebx, [rdi+20h]
0x180025af7  mov     dword ptr [rdi+24h], 0
0x180025afe  call    cs:__imp_GetCurrentThread
0x180025b04  mov     rcx, rax; hThread
0x180025b07  mov     edx, ebx; nPriority
0x180025b09  call    cs:__imp_SetThreadPriority
0x180025b0f  jmp     short loc_180025ABC
0x180025b11  mov     ecx, [rdi+18h]
0x180025b14  xor     edx, edx
0x180025b16  mov     dword ptr [rdi+1Ch], 0
0x180025b1d  call    cs:__imp_?SetThreadIOPriority@@YAJW4_PRIORITY_HINT@@PEAX@Z; SetThreadIOPriority(_PRIORITY_HINT,void *)
0x180025b23  test    eax, eax
0x180025b25  jns     short loc_180025AC2
0x180025b27  mov     r9d, 2DBh
0x180025b2d  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\UserDat"...
0x180025b34  xor     edx, edx
0x180025b36  mov     ecx, eax
0x180025b38  call    Log_UnistoreHREvent_0
0x180025b3d  jmp     short loc_180025AC2
```
