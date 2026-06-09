# DelayLoadUalApi(void)

- ea: `0x18001b694`
- end: `0x18001b73f`
- name: `?DelayLoadUalApi@@YAHXZ`
- size: `171`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000aa50`
- `0x18000d380`

## callees

- `0x18001b694`
- `0x18001b748`
- `0x18001ba10`
- `0x18001d010`

## string_xrefs

- `0x18001b6d1`: `Error loading ualapi.dll.`
- `0x18001b704`: `Error loading ualapi.dll.`

## pseudocode

```c
__int64 __fastcall DelayLoadUalApi(const CHAR *a1)
{
  unsigned int AllImportsForDll; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // r8

  if ( !dword_180028B9C )
  {
    dword_180028B9C = 1;
    AllImportsForDll = _HrLoadAllImportsForDll(a1);
    if ( (int)ElValidateHr_0(AllImportsForDll, v2, v3, 95) >= 0 )
      goto LABEL_6;
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(0x80000u, L"Error loading ualapi.dll.");
    if ( (int)ElValidateHr_0(2147943685LL, v4, v5, 99) >= 0 )
LABEL_6:
      dword_180028B98 = 1;
  }
  return (unsigned int)dword_180028B98;
}

```

## disassembly

```asm
0x18001b694  sub     rsp, 28h
0x18001b698  cmp     cs:dword_180028B9C, 0
0x18001b69f  jnz     loc_18001B733
0x18001b6a5  mov     cs:dword_180028B9C, 1
0x18001b6af  call    __HrLoadAllImportsForDll
0x18001b6b4  mov     r9d, 5Fh ; '_'
0x18001b6ba  mov     ecx, eax
0x18001b6bc  call    ElValidateHr_0
0x18001b6c1  test    eax, eax
0x18001b6c3  jns     short loc_18001B6F6
0x18001b6c5  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001b6cc  test    rax, rax
0x18001b6cf  jz      short loc_18001B6E2
0x18001b6d1  lea     rdx, aErrorLoadingUa; "Error loading ualapi.dll."
0x18001b6d8  mov     ecx, 80000h
0x18001b6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6e2  mov     ecx, 80070505h
0x18001b6e7  mov     r9d, 63h ; 'c'
0x18001b6ed  call    ElValidateHr_0
0x18001b6f2  test    eax, eax
0x18001b6f4  js      short loc_18001B733
0x18001b6f6  jmp     short loc_18001B729
0x18001b6f8  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001b6ff  test    rax, rax
0x18001b702  jz      short loc_18001B715
0x18001b704  lea     rdx, aErrorLoadingUa; "Error loading ualapi.dll."
0x18001b70b  mov     ecx, 80000h
0x18001b710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b715  mov     ecx, 80070505h
0x18001b71a  mov     r9d, 6Fh ; 'o'
0x18001b720  call    ElValidateHr_0
0x18001b725  test    eax, eax
0x18001b727  js      short loc_18001B733
0x18001b729  mov     cs:dword_180028B98, 1
0x18001b733  mov     eax, cs:dword_180028B98
0x18001b739  add     rsp, 28h
0x18001b73d  retn
0x18001c5c6  push    rbp
0x18001c5c8  sub     rsp, 20h
0x18001c5cc  mov     rbp, rdx
0x18001c5cf  mov     rax, [rcx]
0x18001c5d2  cmp     dword ptr [rax], 0C06D007Eh
0x18001c5d8  jz      short loc_18001C5E6
0x18001c5da  cmp     dword ptr [rax], 0C06D007Fh
0x18001c5e0  jz      short loc_18001C5E6
0x18001c5e2  xor     eax, eax
0x18001c5e4  jmp     short loc_18001C5EB
0x18001c5e6  mov     eax, 1
0x18001c5eb  add     rsp, 20h
0x18001c5ef  pop     rbp
0x18001c5f0  retn
```
