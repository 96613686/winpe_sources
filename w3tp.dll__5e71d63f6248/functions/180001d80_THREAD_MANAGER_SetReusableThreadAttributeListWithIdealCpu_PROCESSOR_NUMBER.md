# THREAD_MANAGER::SetReusableThreadAttributeListWithIdealCpu(_PROCESSOR_NUMBER *)

- ea: `0x180001d80`
- end: `0x180001e41`
- name: `?SetReusableThreadAttributeListWithIdealCpu@THREAD_MANAGER@@AEAAHPEAU_PROCESSOR_NUMBER@@@Z`
- size: `193`
- prototype: `int(THREAD_MANAGER *__hidden this, struct _PROCESSOR_NUMBER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001b40`

## callees

- `0x180001d80`
- `0x1800041a6`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180001e25`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180001e25`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180001d9f`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180001d9f`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180001de4`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180001de4`

## pseudocode

```c
_BOOL8 __fastcall THREAD_MANAGER::SetReusableThreadAttributeListWithIdealCpu(
        THREAD_MANAGER *this,
        struct _PROCESSOR_NUMBER *a2)
{
  struct _PROC_THREAD_ATTRIBUTE_LIST *v4; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v5; // rcx
  ULONG_PTR Size; // [rsp+70h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 46) )
  {
    DeleteProcThreadAttributeList(*((LPPROC_THREAD_ATTRIBUTE_LIST *)this + 21));
    memset_0(*((void **)this + 21), 0, *((_QWORD *)this + 22));
    *((_DWORD *)this + 46) = 0;
  }
  v4 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)*((_QWORD *)this + 21);
  Size = *((_QWORD *)this + 22);
  if ( !InitializeProcThreadAttributeList(v4, 1u, 0, &Size) )
    return 0;
  v5 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)*((_QWORD *)this + 21);
  *((_DWORD *)this + 46) = 1;
  return UpdateProcThreadAttribute(v5, 0, 0x30005u, a2, 4u, 0, 0);
}

```

## disassembly

```asm
0x180001d80  push    rbx
0x180001d82  push    rbp
0x180001d83  push    rsi
0x180001d84  push    rdi
0x180001d85  sub     rsp, 48h
0x180001d89  cmp     dword ptr [rcx+0B8h], 0
0x180001d90  mov     rbp, rdx
0x180001d93  mov     rsi, rcx
0x180001d96  jz      short loc_180001DC4
0x180001d98  mov     rcx, [rcx+0A8h]; lpAttributeList
0x180001d9f  call    cs:__imp_DeleteProcThreadAttributeList
0x180001da5  mov     r8, [rsi+0B0h]; Size
0x180001dac  xor     edx, edx; Val
0x180001dae  mov     rcx, [rsi+0A8h]; void *
0x180001db5  call    memset_0
0x180001dba  mov     dword ptr [rsi+0B8h], 0
0x180001dc4  mov     rax, [rsi+0B0h]
0x180001dcb  lea     r9, [rsp+68h+Size]; lpSize
0x180001dd0  mov     rcx, [rsi+0A8h]; lpAttributeList
0x180001dd7  xor     r8d, r8d; dwFlags
0x180001dda  mov     edx, 1; dwAttributeCount
0x180001ddf  mov     [rsp+68h+Size], rax
0x180001de4  call    cs:__imp_InitializeProcThreadAttributeList
0x180001dea  test    eax, eax
0x180001dec  jz      short loc_180001E36
0x180001dee  mov     rcx, [rsi+0A8h]; lpAttributeList
0x180001df5  mov     r9, rbp; lpValue
0x180001df8  mov     [rsp+68h+lpReturnSize], 0; lpReturnSize
0x180001e01  xor     edx, edx; dwFlags
0x180001e03  mov     [rsp+68h+lpPreviousValue], 0; lpPreviousValue
0x180001e0c  mov     r8d, 30005h; Attribute
0x180001e12  mov     [rsp+68h+cbSize], 4; cbSize
0x180001e1b  mov     dword ptr [rsi+0B8h], 1
0x180001e25  call    cs:__imp_UpdateProcThreadAttribute
0x180001e2b  xor     ecx, ecx
0x180001e2d  test    eax, eax
0x180001e2f  setnz   cl
0x180001e32  mov     eax, ecx
0x180001e34  jmp     short loc_180001E38
0x180001e36  xor     eax, eax
0x180001e38  add     rsp, 48h
0x180001e3c  pop     rdi
0x180001e3d  pop     rsi
0x180001e3e  pop     rbp
0x180001e3f  pop     rbx
0x180001e40  retn
```
