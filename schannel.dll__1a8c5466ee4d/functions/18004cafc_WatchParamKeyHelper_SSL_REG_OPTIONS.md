# WatchParamKeyHelper(SSL_REG_OPTIONS *)

- ea: `0x18004cafc`
- end: `0x18004cbd5`
- name: `?WatchParamKeyHelper@@YAKPEAUSSL_REG_OPTIONS@@@Z`
- size: `217`
- prototype: `unsigned int __fastcall(PVOID pvContext)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180053d90`
- `0x180069730`
- `0x180069900`
- `0x18006a7d0`

## callees

- `0x18004cafc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004cb7f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004cb7f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004cb5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004cb5f`
- `ntdll!RtlRegisterWait` at `0x18004cbc2`
- `ntdll!RtlRegisterWait` at `0x18004cbc2`
- `ntdll!RtlDeregisterWait` at `0x18004cb8f`
- `ntdll!RtlDeregisterWait` at `0x18004cb8f`

## pseudocode

```c
LSTATUS __fastcall WatchParamKeyHelper(char *pvContext)
{
  HKEY *v2; // rdi
  LSTATUS result; // eax
  LSTATUS v4; // edi
  NTSTATUS v5; // eax
  DWORD v6; // [rsp+60h] [rbp+8h] BYREF

  v6 = 0;
  if ( !pvContext )
    return 0;
  v2 = (HKEY *)(pvContext + 16);
  if ( *((_QWORD *)pvContext + 2)
    || (result = RegCreateKeyExW(
                   HKEY_LOCAL_MACHINE,
                   *((LPCWSTR *)pvContext + 3),
                   0,
                   (LPWSTR)&Class,
                   0,
                   0x20019u,
                   0,
                   v2,
                   &v6)) == 0 )
  {
    v4 = RegNotifyChangeKeyValue(*v2, 1, 0x10000005u, *((HANDLE *)pvContext + 1), 1);
    if ( !*(_QWORD *)pvContext || (v5 = RtlDeregisterWait(*(HANDLE *)pvContext), *(_QWORD *)pvContext = 0, v5 >= 0) )
    {
      if ( !v4 )
        RtlRegisterWait(
          (PHANDLE)pvContext,
          *((HANDLE *)pvContext + 1),
          *((WAITORTIMERCALLBACKFUNC *)pvContext + 4),
          pvContext,
          0xFFFFFFFF,
          0x48u);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004cafc  mov     r11, rsp
0x18004caff  mov     [r11+10h], rbx
0x18004cb03  push    rdi
0x18004cb04  sub     rsp, 50h
0x18004cb08  mov     [rsp+58h+arg_0], 0
0x18004cb10  mov     rbx, rcx
0x18004cb13  test    rcx, rcx
0x18004cb16  jz      loc_18004CBC8
0x18004cb1c  lea     rdi, [rcx+10h]
0x18004cb20  cmp     qword ptr [rdi], 0
0x18004cb24  jnz     short loc_18004CB69
0x18004cb26  mov     rdx, [rcx+18h]; lpSubKey
0x18004cb2a  lea     rax, [r11+8]
0x18004cb2e  mov     [r11-18h], rax
0x18004cb32  lea     r9, Class; lpClass
0x18004cb39  mov     [r11-20h], rdi
0x18004cb3d  xor     r8d, r8d; Reserved
0x18004cb40  mov     qword ptr [r11-28h], 0
0x18004cb48  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004cb4f  mov     [rsp+58h+samDesired], 20019h; samDesired
0x18004cb57  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18004cb5f  call    cs:__imp_RegCreateKeyExW
0x18004cb65  test    eax, eax
0x18004cb67  jnz     short loc_18004CBCA
0x18004cb69  mov     r9, [rbx+8]; hEvent
0x18004cb6d  mov     edx, 1; bWatchSubtree
0x18004cb72  mov     rcx, [rdi]; hKey
0x18004cb75  mov     r8d, 10000005h; dwNotifyFilter
0x18004cb7b  mov     [rsp+58h+dwOptions], edx; fAsynchronous
0x18004cb7f  call    cs:__imp_RegNotifyChangeKeyValue
0x18004cb85  mov     rcx, [rbx]; hWaitHandle
0x18004cb88  mov     edi, eax
0x18004cb8a  test    rcx, rcx
0x18004cb8d  jz      short loc_18004CBA0
0x18004cb8f  call    cs:__imp_RtlDeregisterWait
0x18004cb95  mov     qword ptr [rbx], 0
0x18004cb9c  test    eax, eax
0x18004cb9e  js      short loc_18004CBC8
0x18004cba0  test    edi, edi
0x18004cba2  jnz     short loc_18004CBC8
0x18004cba4  mov     r8, [rbx+20h]; Callback
0x18004cba8  mov     r9, rbx; pvContext
0x18004cbab  mov     rdx, [rbx+8]; hObject
0x18004cbaf  mov     rcx, rbx; phNewWaitObject
0x18004cbb2  mov     [rsp+58h+samDesired], 48h ; 'H'; ulFlags
0x18004cbba  mov     [rsp+58h+dwOptions], 0FFFFFFFFh; ulMilliseconds
0x18004cbc2  call    cs:__imp_RtlRegisterWait
0x18004cbc8  xor     eax, eax
0x18004cbca  mov     rbx, [rsp+58h+arg_8]
0x18004cbcf  add     rsp, 50h
0x18004cbd3  pop     rdi
0x18004cbd4  retn
```
