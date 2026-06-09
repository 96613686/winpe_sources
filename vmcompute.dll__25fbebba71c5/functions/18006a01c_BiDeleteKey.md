# BiDeleteKey

- ea: `0x18006a01c`
- end: `0x18006a130`
- name: `BiDeleteKey`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180063dcc`
- `0x180064a8c`
- `0x18006a01c`

## callees

- `0x18006994c`
- `0x18006a01c`
- `0x18006a2d4`
- `0x18006a3ac`
- `0x18006b024`
- `0x18006fbc0`
- `0x1800702a4`

## import_xrefs

- `ntdll!ZwClose` at `0x18006a116`
- `ntdll!ZwClose` at `0x18006a116`
- `ntdll!ZwDeleteKey` at `0x18006a0eb`
- `ntdll!ZwDeleteKey` at `0x18006a0eb`
- `ntdll!RtlFreeHeap` at `0x18006a0ba`
- `ntdll!RtlFreeHeap` at `0x18006a0ba`

## pseudocode

```c
__int64 __fastcall BiDeleteKey(__int64 a1)
{
  unsigned __int64 v1; // rbx
  int v2; // eax
  const WCHAR **v3; // r14
  unsigned int v4; // esi
  __int64 i; // rdi
  unsigned __int64 v6; // rdi
  unsigned int v7; // eax
  NTSTATUS v8; // eax
  unsigned int v9; // ebp
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp+10h] BYREF
  PVOID P; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  v1 = a1 & 0xFFFFFFFFFFFFFFFDuLL;
  Handle = 0;
  P = 0;
  v2 = BiEnumerateSubKeys(a1 & 0xFFFFFFFFFFFFFFFDuLL, &P, &v11);
  v3 = (const WCHAR **)P;
  if ( v2 >= 0 )
  {
    v4 = v11;
    for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
    {
      if ( (int)BiOpenKey(v1, v3[i], 983103, &Handle) >= 0 && (int)BiDeleteKey(Handle) < 0 )
        BiCloseKey(Handle);
    }
  }
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( (v1 & 1) != 0 )
  {
    v6 = v1 & 0xFFFFFFFFFFFFFFFEuLL;
    v7 = ORDeleteKey(v1 & 0xFFFFFFFFFFFFFFFEuLL, 0);
    v8 = BiDosErrorToNtStatus(v7);
  }
  else
  {
    v8 = ZwDeleteKey((HANDLE)v1);
    v6 = v1 & 0xFFFFFFFFFFFFFFFEuLL;
  }
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( (v1 & 1) != 0 )
      ORCloseKey(v6);
    else
      ZwClose((HANDLE)v1);
  }
  return v9;
}

```

## disassembly

```asm
0x18006a01c  mov     rax, rsp
0x18006a01f  push    rbx
0x18006a020  push    rbp
0x18006a021  push    rsi
0x18006a022  push    rdi
0x18006a023  push    r14
0x18006a025  sub     rsp, 20h
0x18006a029  mov     rbx, rcx
0x18006a02c  mov     dword ptr [rax+8], 0
0x18006a033  and     rbx, 0FFFFFFFFFFFFFFFDh
0x18006a037  mov     qword ptr [rax+10h], 0
0x18006a03f  mov     rcx, rbx
0x18006a042  mov     qword ptr [rax+18h], 0
0x18006a04a  lea     r8, [rax+8]
0x18006a04e  lea     rdx, [rax+18h]
0x18006a052  call    BiEnumerateSubKeys
0x18006a057  mov     r14, [rsp+48h+P]
0x18006a05c  test    eax, eax
0x18006a05e  js      short loc_18006A0A3
0x18006a060  mov     esi, [rsp+48h+arg_0]
0x18006a064  xor     edi, edi
0x18006a066  test    esi, esi
0x18006a068  jz      short loc_18006A0A3
0x18006a06a  mov     rdx, [r14+rdi*8]
0x18006a06e  lea     r9, [rsp+48h+Handle]
0x18006a073  mov     r8d, 0F003Fh
0x18006a079  mov     rcx, rbx
0x18006a07c  call    BiOpenKey
0x18006a081  test    eax, eax
0x18006a083  js      short loc_18006A09D
0x18006a085  mov     rcx, [rsp+48h+Handle]
0x18006a08a  call    BiDeleteKey
0x18006a08f  test    eax, eax
0x18006a091  jns     short loc_18006A09D
0x18006a093  mov     rcx, [rsp+48h+Handle]; Handle
0x18006a098  call    BiCloseKey
0x18006a09d  inc     edi
0x18006a09f  cmp     edi, esi
0x18006a0a1  jb      short loc_18006A06A
0x18006a0a3  test    r14, r14
0x18006a0a6  jz      short loc_18006A0C6
0x18006a0a8  mov     rcx, gs:60h
0x18006a0b1  mov     r8, r14; P
0x18006a0b4  xor     edx, edx; Flags
0x18006a0b6  mov     rcx, [rcx+30h]; HeapHandle
0x18006a0ba  call    cs:__imp_RtlFreeHeap
0x18006a0c1  nop     dword ptr [rax+rax+00h]
0x18006a0c6  mov     rsi, rbx
0x18006a0c9  and     esi, 1
0x18006a0cc  jz      short loc_18006A0E8
0x18006a0ce  mov     rdi, rbx
0x18006a0d1  xor     edx, edx
0x18006a0d3  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18006a0d7  mov     rcx, rdi
0x18006a0da  call    ORDeleteKey
0x18006a0df  mov     ecx, eax
0x18006a0e1  call    BiDosErrorToNtStatus
0x18006a0e6  jmp     short loc_18006A0FE
0x18006a0e8  mov     rcx, rbx; KeyHandle
0x18006a0eb  call    cs:__imp_ZwDeleteKey
0x18006a0f2  nop     dword ptr [rax+rax+00h]
0x18006a0f7  mov     rdi, rbx
0x18006a0fa  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18006a0fe  mov     ebp, eax
0x18006a100  test    eax, eax
0x18006a102  js      short loc_18006A122
0x18006a104  test    rsi, rsi
0x18006a107  jz      short loc_18006A113
0x18006a109  mov     rcx, rdi
0x18006a10c  call    ORCloseKey
0x18006a111  jmp     short loc_18006A122
0x18006a113  mov     rcx, rbx; Handle
0x18006a116  call    cs:__imp_ZwClose
0x18006a11d  nop     dword ptr [rax+rax+00h]
0x18006a122  mov     eax, ebp
0x18006a124  add     rsp, 20h
0x18006a128  pop     r14
0x18006a12a  pop     rdi
0x18006a12b  pop     rsi
0x18006a12c  pop     rbp
0x18006a12d  pop     rbx
0x18006a12e  retn
```
