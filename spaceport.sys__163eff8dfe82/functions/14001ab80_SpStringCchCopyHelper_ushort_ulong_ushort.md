# SpStringCchCopyHelper(ushort *,ulong,ushort * *)

- ea: `0x14001ab80`
- end: `0x14001ac8d`
- name: `?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z`
- size: `269`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a880`
- `0x140042dd4`
- `0x14005cb30`
- `0x14005cca0`
- `0x14005cf80`
- `0x14005d250`
- `0x14005e658`
- `0x14005f56c`
- `0x14009365c`
- `0x140093b94`
- `0x140098cd8`
- `0x14009c600`
- `0x14009cdc0`
- `0x1400a0274`
- `0x1400a1888`
- `0x1400a9bc4`
- `0x1400a9f10`

## callees

- `0x14001ab80`
- `0x14001aca0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001abf3`
- `ntoskrnl!ExAllocatePool2` at `0x14001abf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac31`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac31`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac7a`

## pseudocode

```c
__int64 __fastcall SpStringCchCopyHelper(unsigned __int16 *a1, unsigned int a2, PVOID *a3)
{
  __int64 v4; // rsi
  __int64 result; // rax
  __int64 v7; // r8
  unsigned __int64 v8; // rsi
  unsigned __int16 *Pool2; // rax
  void *v10; // r10
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rax

  v4 = a2;
  if ( *a3 )
  {
    ExFreePoolWithTag(*a3, 0);
    *a3 = 0;
  }
  if ( !a1 || (unsigned int)v4 > 0x7FFFFFFF )
    return 3221225485LL;
  v12 = v4;
  v13 = a1;
  if ( (_DWORD)v4 )
  {
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v12;
    }
    while ( v12 );
  }
  result = 3221225485LL;
  if ( v12 )
    result = 0;
  v7 = v4 - v12;
  if ( v12 && v7 )
  {
    v8 = v7 + 1;
    Pool2 = (unsigned __int16 *)ExAllocatePool2(64, 2 * (v7 + 1), 1482190931);
    if ( Pool2 )
    {
      result = RtlStringCchCopyW(Pool2, v8, a1);
      v11 = result;
      if ( (int)result < 0 )
      {
        ExFreePoolWithTag(v10, 0);
        return v11;
      }
      else
      {
        *a3 = v10;
      }
    }
    else
    {
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001ab80  mov     [rsp+arg_0], rbx
0x14001ab85  mov     [rsp+arg_8], rsi
0x14001ab8a  push    rdi
0x14001ab8b  sub     rsp, 20h
0x14001ab8f  mov     rbx, rcx
0x14001ab92  mov     esi, edx
0x14001ab94  mov     rcx, [r8]; P
0x14001ab97  mov     rdi, r8
0x14001ab9a  test    rcx, rcx
0x14001ab9d  jnz     loc_14001AC2F
0x14001aba3  test    rbx, rbx
0x14001aba6  jnz     loc_14001AC49
0x14001abac  mov     eax, 0C000000Dh
0x14001abb1  mov     rbx, [rsp+28h+arg_0]
0x14001abb6  mov     rsi, [rsp+28h+arg_8]
0x14001abbb  add     rsp, 20h
0x14001abbf  pop     rdi
0x14001abc0  retn
0x14001abc2  xor     ecx, ecx
0x14001abc4  mov     eax, 0C000000Dh
0x14001abc9  test    rdx, rdx
0x14001abcc  cmovnz  eax, ecx
0x14001abcf  sub     r8, rdx
0x14001abd2  test    rdx, rdx
0x14001abd5  cmovnz  rcx, r8
0x14001abd9  jz      short loc_14001ABB1
0x14001abdb  test    rcx, rcx
0x14001abde  jz      short loc_14001ABB1
0x14001abe0  lea     rsi, [rcx+1]
0x14001abe4  mov     r8d, 58587053h
0x14001abea  lea     rdx, [rsi+rsi]
0x14001abee  mov     ecx, 40h ; '@'
0x14001abf3  call    cs:__imp_ExAllocatePool2
0x14001abfa  nop     dword ptr [rax+rax+00h]
0x14001abff  mov     r10, rax
0x14001ac02  test    rax, rax
0x14001ac05  jz      short loc_14001AC6B
0x14001ac07  mov     r8, rbx; unsigned __int16 *
0x14001ac0a  mov     rdx, rsi; unsigned __int64
0x14001ac0d  mov     rcx, rax; unsigned __int16 *
0x14001ac10  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001ac15  mov     ebx, eax
0x14001ac17  test    eax, eax
0x14001ac19  js      short loc_14001AC75
0x14001ac1b  mov     rbx, [rsp+28h+arg_0]
0x14001ac20  mov     rsi, [rsp+28h+arg_8]
0x14001ac25  mov     [rdi], r10
0x14001ac28  add     rsp, 20h
0x14001ac2c  pop     rdi
0x14001ac2d  retn
0x14001ac2f  xor     edx, edx; Tag
0x14001ac31  call    cs:__imp_ExFreePoolWithTag
0x14001ac38  nop     dword ptr [rax+rax+00h]
0x14001ac3d  mov     qword ptr [rdi], 0
0x14001ac44  jmp     loc_14001ABA3
0x14001ac49  cmp     esi, 7FFFFFFFh
0x14001ac4f  ja      loc_14001ABAC
0x14001ac55  mov     rdx, rsi
0x14001ac58  mov     rax, rbx
0x14001ac5b  mov     r8, rsi
0x14001ac5e  test    esi, esi
0x14001ac60  jz      loc_14001ABC2
0x14001ac66  jmp     loc_14006ADA0
0x14001ac6b  mov     eax, 0C000009Ah
0x14001ac70  jmp     loc_14001ABB1
0x14001ac75  xor     edx, edx; Tag
0x14001ac77  mov     rcx, r10; P
0x14001ac7a  call    cs:__imp_ExFreePoolWithTag
0x14001ac81  nop     dword ptr [rax+rax+00h]
0x14001ac86  mov     eax, ebx
0x14001ac88  jmp     loc_14001ABB1
0x14006ada0  cmp     word ptr [rax], 0
0x14006ada4  jz      loc_14001ABC2
0x14006adaa  add     rax, 2
0x14006adae  sub     rdx, 1
0x14006adb2  jnz     short loc_14006ADA0
0x14006adb4  jmp     loc_14001ABC2
```
