# DllMain

- ea: `0x18000c7f0`
- end: `0x18000c871`
- name: `DllMain`
- size: `129`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000c7f0`
- `0x18000c878`
- `0x180018628`
- `0x18001870c`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  BOOL result; // eax
  BOOL v7; // ebp

  if ( fdwReason - 1 > 1 || (result = ((__int64 (*)(void))CRT_INIT)()) )
  {
    DllMainCRTStartupForGS2(hinstDLL, fdwReason, lpReserved);
    result = _DllMain(hinstDLL, fdwReason, (__int64)lpReserved);
    v7 = result;
    if ( !fdwReason || fdwReason == 3 )
    {
      if ( !(unsigned int)CRT_INIT(hinstDLL, fdwReason, lpReserved) )
        return 0;
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c7f0  mov     [rsp+arg_8], rbx
0x18000c7f5  mov     [rsp+arg_10], rsi
0x18000c7fa  push    rdi
0x18000c7fb  sub     rsp, 20h
0x18000c7ff  lea     eax, [rdx-1]
0x18000c802  mov     rdi, r8
0x18000c805  mov     ebx, edx
0x18000c807  mov     rsi, rcx
0x18000c80a  cmp     eax, 1
0x18000c80d  ja      short loc_18000C828
0x18000c80f  call    _CRT_INIT
0x18000c814  test    eax, eax
0x18000c816  jnz     short loc_18000C828
0x18000c818  mov     rbx, [rsp+28h+arg_8]
0x18000c81d  mov     rsi, [rsp+28h+arg_10]
0x18000c822  add     rsp, 20h
0x18000c826  pop     rdi
0x18000c827  retn
0x18000c828  mov     r8, rdi
0x18000c82b  mov     [rsp+28h+arg_0], rbp
0x18000c830  mov     edx, ebx
0x18000c832  mov     rcx, rsi
0x18000c835  call    _DllMainCRTStartupForGS2
0x18000c83a  mov     r8, rdi; void *
0x18000c83d  mov     edx, ebx; unsigned int
0x18000c83f  mov     rcx, rsi; hLibModule
0x18000c842  call    ?_DllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z; _DllMain(HINSTANCE__ *,ulong,void *)
0x18000c847  mov     ebp, eax
0x18000c849  test    ebx, ebx
0x18000c84b  jnz     short loc_18000C86A
0x18000c84d  mov     r8, rdi
0x18000c850  mov     edx, ebx
0x18000c852  mov     rcx, rsi
0x18000c855  call    _CRT_INIT
0x18000c85a  xor     ecx, ecx
0x18000c85c  test    eax, eax
0x18000c85e  cmovz   ebp, ecx
0x18000c861  mov     eax, ebp
0x18000c863  mov     rbp, [rsp+28h+arg_0]
0x18000c868  jmp     short loc_18000C818
0x18000c86a  cmp     ebx, 3
0x18000c86d  jnz     short loc_18000C863
0x18000c86f  jmp     short loc_18000C84D
```
