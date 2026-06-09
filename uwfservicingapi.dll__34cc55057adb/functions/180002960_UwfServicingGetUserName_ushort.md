# UwfServicingGetUserName(ushort * *)

- ea: `0x180002960`
- end: `0x180002a19`
- name: `?UwfServicingGetUserName@@YAJPEAPEAG@Z`
- size: `185`
- prototype: `int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800027c8`

## callees

- `0x180002960`
- `0x180002f14`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180002a0f`
- `msvcrt!wcscpy_s` at `0x180002a0f`
- `msvcrt!malloc` at `0x1800029e0`
- `msvcrt!malloc` at `0x1800029e0`

## string_xrefs

- `0x180002997`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing\Config`

## pseudocode

```c
int __fastcall UwfServicingGetUserName(unsigned __int16 **a1)
{
  int result; // eax
  unsigned __int16 *v3; // rbx
  char *v4; // rax
  unsigned int v5; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v6; // [rsp+58h] [rbp+28h] BYREF
  void *v7; // [rsp+60h] [rbp+30h] BYREF

  v7 = 0;
  v5 = 0;
  v6 = 0;
  result = UwfServicingRegGetValue(
             (HKEY)a1,
             L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing\\Config",
             L"UwfUserName",
             &v6,
             &v7,
             &v5);
  if ( !result )
  {
    if ( v5 < 2 || v6 != 1 )
      result = -2147024883;
    goto LABEL_5;
  }
  if ( result != -2147024894 )
  {
LABEL_5:
    v3 = (unsigned __int16 *)v7;
    goto LABEL_6;
  }
  v5 = 30;
  v4 = (char *)malloc(0x1Eu);
  v3 = (unsigned __int16 *)v4;
  if ( v4 )
  {
    *(_OWORD *)v4 = 0;
    *(_OWORD *)(v4 + 14) = 0;
    wcscpy_s((wchar_t *)v4, (unsigned __int64)v5 >> 1, L"UWF-Servicing");
    result = 0;
  }
  else
  {
    result = -2147024882;
  }
LABEL_6:
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180002960  push    rbp
0x180002962  push    rbx
0x180002963  push    rdi
0x180002964  mov     rbp, rsp
0x180002967  sub     rsp, 30h
0x18000296b  lea     rax, [rbp+arg_0]
0x18000296f  mov     [rbp+arg_10], 0
0x180002977  mov     [rsp+30h+var_8], rax; unsigned int *
0x18000297c  lea     r9, [rbp+arg_8]; unsigned int *
0x180002980  lea     rax, [rbp+arg_10]
0x180002984  mov     [rbp+arg_0], 0
0x18000298b  lea     r8, aUwfusername; "UwfUserName"
0x180002992  mov     [rsp+30h+var_10], rax; void **
0x180002997  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x18000299e  mov     [rbp+arg_8], 0
0x1800029a5  mov     rdi, rcx
0x1800029a8  call    ?UwfServicingRegGetValue@@YAJPEAUHKEY__@@PEBG1PEAKPEAPEAX2@Z; UwfServicingRegGetValue(HKEY__ *,ushort const *,ushort const *,ulong *,void * *,ulong *)
0x1800029ad  test    eax, eax
0x1800029af  jnz     short loc_1800029D1
0x1800029b1  cmp     [rbp+arg_0], 2
0x1800029b5  jb      short loc_1800029BD
0x1800029b7  cmp     [rbp+arg_8], 1
0x1800029bb  jz      short loc_1800029C2
0x1800029bd  mov     eax, 8007000Dh
0x1800029c2  mov     rbx, [rbp+arg_10]
0x1800029c6  mov     [rdi], rbx
0x1800029c9  add     rsp, 30h
0x1800029cd  pop     rdi
0x1800029ce  pop     rbx
0x1800029cf  pop     rbp
0x1800029d0  retn
0x1800029d1  cmp     eax, 80070002h
0x1800029d6  jnz     short loc_1800029C2
0x1800029d8  mov     ecx, 1Eh; Size
0x1800029dd  mov     [rbp+arg_0], ecx
0x1800029e0  call    cs:__imp_malloc
0x1800029e6  mov     rbx, rax
0x1800029e9  test    rax, rax
0x1800029ec  jnz     short loc_1800029F5
0x1800029ee  mov     eax, 8007000Eh
0x1800029f3  jmp     short loc_1800029C6
0x1800029f5  xorps   xmm0, xmm0
0x1800029f8  lea     r8, aUwfServicing; "UWF-Servicing"
0x1800029ff  movups  xmmword ptr [rbx], xmm0
0x180002a02  mov     rcx, rbx; Destination
0x180002a05  movups  xmmword ptr [rbx+0Eh], xmm0
0x180002a09  mov     edx, [rbp+arg_0]
0x180002a0c  shr     rdx, 1; SizeInWords
0x180002a0f  call    cs:__imp_wcscpy_s
0x180002a15  xor     eax, eax
0x180002a17  jmp     short loc_1800029C6
```
