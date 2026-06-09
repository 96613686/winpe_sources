# GetConfigValue

- ea: `0x140010f80`
- end: `0x140011035`
- name: `GetConfigValue`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14000a6cc`
- `0x140010f80`
- `0x140014e00`
- `0x140015100`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140010ff0`
- `ntoskrnl!ExAllocatePool2` at `0x140010ff0`

## pseudocode

```c
__int64 __fastcall GetConfigValue(__int64 a1, int a2, const void *a3, unsigned int a4, __int64 a5, _QWORD *a6)
{
  unsigned int v7; // ebx
  void *Pool2; // rax
  void *v11; // rdi
  char v12; // [rsp+28h] [rbp-30h]

  if ( a2 != 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(g_RecorderLog, a2, 8, 10, (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids, v12);
    }
    return (unsigned int)-1073741811;
  }
  if ( !a4 )
    return (unsigned int)-1073741811;
  Pool2 = (void *)ExAllocatePool2(256, a4, 1130525525);
  v11 = Pool2;
  if ( Pool2 )
  {
    v7 = 0;
    memset(Pool2, 0, a4);
    memmove(v11, a3, a4);
    *a6 = v11;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v7;
}

```

## disassembly

```asm
0x140010f80  push    rbx
0x140010f82  push    rbp
0x140010f83  push    rsi
0x140010f84  push    rdi
0x140010f85  sub     rsp, 38h
0x140010f89  mov     rbp, r8
0x140010f8c  cmp     edx, 1
0x140010f8f  jz      short loc_140010FDA
0x140010f91  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140010f98  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010f9f  jz      short loc_140010FC9
0x140010fa1  mov     rcx, cs:g_RecorderLog
0x140010fa8  lea     rax, WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids
0x140010faf  mov     dword ptr [rsp+58h+var_30], edx
0x140010fb3  mov     r9d, 0Ah
0x140010fb9  mov     dl, 2
0x140010fbb  mov     [rsp+58h+var_38], rax
0x140010fc0  lea     r8d, [r9-2]
0x140010fc4  call    WPP_RECORDER_SF_d
0x140010fc9  mov     ebx, 0C000000Dh
0x140010fce  mov     eax, ebx
0x140010fd0  add     rsp, 38h
0x140010fd4  pop     rdi
0x140010fd5  pop     rsi
0x140010fd6  pop     rbp
0x140010fd7  pop     rbx
0x140010fd8  retn
0x140010fda  test    r9d, r9d
0x140010fdd  jz      short loc_140010FC9
0x140010fdf  mov     r8d, 43627355h
0x140010fe5  mov     edx, r9d
0x140010fe8  mov     ecx, 100h
0x140010fed  mov     esi, r9d
0x140010ff0  call    cs:__imp_ExAllocatePool2
0x140010ff7  nop     dword ptr [rax+rax+00h]
0x140010ffc  mov     rdi, rax
0x140010fff  test    rax, rax
0x140011002  jz      short loc_14001102E
0x140011004  mov     r8d, esi; Size
0x140011007  xor     edx, edx; Val
0x140011009  mov     rcx, rax; void *
0x14001100c  xor     ebx, ebx
0x14001100e  call    memset
0x140011013  mov     r8d, esi; Size
0x140011016  mov     rdx, rbp; Src
0x140011019  mov     rcx, rdi; void *
0x14001101c  call    memmove
0x140011021  mov     rax, [rsp+58h+arg_28]
0x140011029  mov     [rax], rdi
0x14001102c  jmp     short loc_140010FCE
0x14001102e  mov     ebx, 0C000009Ah
0x140011033  jmp     short loc_140010FCE
```
