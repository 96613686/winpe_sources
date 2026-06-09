# TraceLoggingRegister_EventRegister_2U

- ea: `0x140001214`
- end: `0x14000132d`
- name: `TraceLoggingRegister_EventRegister_2U`
- size: `281`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000c1a0`

## callees

- `0x140001214`
- `0x140001656`
- `0x140001686`
- `0x1400016aa`
- `0x14002e420`
- `0x14002f010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x140001279`
- `ADVAPI32!EventRegister` at `0x140001279`

## string_xrefs

- `0x1400012a2`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1400012c7`: `advapi32.dll`

## pseudocode

```c
__int64 TraceLoggingRegister_EventRegister_2U()
{
  signed int v0; // eax
  unsigned int v1; // ebx
  void *v2; // rdi
  unsigned int v3; // esi
  FARPROC EventSetInformation; // rax
  HMODULE phModule; // [rsp+30h] [rbp-28h] BYREF
  GUID ProviderId; // [rsp+38h] [rbp-20h] BYREF

  ProviderId = (GUID)*((_OWORD *)off_140042008 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_140042028 = 0;
  v0 = EventRegister(&ProviderId, (PENABLECALLBACK)tlgEnableCallback, &dword_140042000, &RegHandle);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
      return (unsigned __int16)v0 | 0x80070000;
  }
  else
  {
    v2 = off_140042008;
    phModule = 0;
    v3 = *(unsigned __int16 *)off_140042008;
    if ( GetModuleHandleExW_0(0, L"api-ms-win-eventing-provider-l1-1-0.dll", &phModule)
      || GetModuleHandleExW_0(0, L"advapi32.dll", &phModule) )
    {
      EventSetInformation = GetProcAddress_0(phModule, "EventSetInformation");
      if ( EventSetInformation )
        ((void (__fastcall *)(ULONGLONG, __int64, void *, _QWORD))EventSetInformation)(RegHandle, 2, v2, v3);
      FreeLibrary_0(phModule);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140001214  mov     [rsp+arg_0], rbx
0x140001219  mov     [rsp+arg_8], rsi
0x14000121e  push    rdi
0x14000121f  sub     rsp, 50h
0x140001223  mov     rax, cs:__security_cookie
0x14000122a  xor     rax, rsp
0x14000122d  mov     [rsp+58h+var_10], rax
0x140001232  cmp     cs:RegHandle, 0
0x14000123a  mov     rax, cs:off_140042008; "9"
0x140001241  movups  xmm0, xmmword ptr [rax-10h]
0x140001245  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x14000124b  jz      short loc_140001254
0x14000124d  mov     ecx, 5
0x140001252  int     29h; Win8: RtlFailFast(ecx)
0x140001254  xorps   xmm0, xmm0
0x140001257  lea     r9, RegHandle; RegHandle
0x14000125e  lea     r8, dword_140042000; CallbackContext
0x140001265  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000126c  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x140001271  movdqu  cs:xmmword_140042028, xmm0
0x140001279  call    cs:__imp_EventRegister
0x14000127f  mov     ebx, eax
0x140001281  test    eax, eax
0x140001283  jz      short loc_140001296
0x140001285  jle     loc_14000130E
0x14000128b  movzx   ebx, ax
0x14000128e  or      ebx, 80070000h
0x140001294  jmp     short loc_14000130E
0x140001296  mov     rdi, cs:off_140042008; "9"
0x14000129d  lea     r8, [rsp+58h+phModule]; phModule
0x1400012a2  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x1400012a9  mov     [rsp+58h+phModule], 0
0x1400012b2  xor     ecx, ecx; dwFlags
0x1400012b4  movzx   esi, word ptr [rdi]
0x1400012b7  call    GetModuleHandleExW_0
0x1400012bc  test    eax, eax
0x1400012be  jnz     short loc_1400012D7
0x1400012c0  lea     r8, [rsp+58h+phModule]; phModule
0x1400012c5  xor     ecx, ecx; dwFlags
0x1400012c7  lea     rdx, aAdvapi32Dll_0; "advapi32.dll"
0x1400012ce  call    GetModuleHandleExW_0
0x1400012d3  test    eax, eax
0x1400012d5  jz      short loc_14000130E
0x1400012d7  mov     rcx, [rsp+58h+phModule]; hModule
0x1400012dc  lea     rdx, ProcName; "EventSetInformation"
0x1400012e3  call    GetProcAddress_0
0x1400012e8  test    rax, rax
0x1400012eb  jz      short loc_140001304
0x1400012ed  mov     rcx, cs:RegHandle
0x1400012f4  mov     r9d, esi
0x1400012f7  mov     r8, rdi
0x1400012fa  mov     edx, 2
0x1400012ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001304  mov     rcx, [rsp+58h+phModule]; hLibModule
0x140001309  call    FreeLibrary_0
0x14000130e  mov     eax, ebx
0x140001310  mov     rcx, [rsp+58h+var_10]
0x140001315  xor     rcx, rsp; StackCookie
0x140001318  call    __security_check_cookie
0x14000131d  mov     rbx, [rsp+58h+arg_0]
0x140001322  mov     rsi, [rsp+58h+arg_8]
0x140001327  add     rsp, 50h
0x14000132b  pop     rdi
0x14000132c  retn
```
