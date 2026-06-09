# WinHvDeleteServicePartition

- ea: `0x14001f8b0`
- end: `0x14001f90f`
- name: `WinHvDeleteServicePartition`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x140007760`
- `0x1400077b0`
- `0x14001f8b0`
- `0x1400202cc`
- `0x1400204a4`

## pseudocode

```c
__int64 __fastcall WinHvDeleteServicePartition(__int64 a1)
{
  __int64 result; // rax
  __int64 (__fastcall *v3)(unsigned __int64); // rdx

  if ( *(_BYTE *)a1 )
  {
    result = WinHvSetInterceptRoutine(*(_QWORD *)(a1 + 8), 0, 0);
    if ( (int)result >= 0 )
    {
      result = WinHvSetLowMemoryPolicyRoutine(*(_QWORD *)(a1 + 8), 0, 0);
      if ( (int)result >= 0 )
        return WinHvpDeleteWinHvPartition(*(_QWORD *)(a1 + 8), 1);
    }
  }
  else
  {
    v3 = *(__int64 (__fastcall **)(unsigned __int64))(a1 + 16);
    if ( v3 )
      return WinHvpDeletePartition(*(_QWORD *)(a1 + 8), v3);
    else
      return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x14001f8b0  push    rbx
0x14001f8b2  sub     rsp, 20h
0x14001f8b6  cmp     byte ptr [rcx], 0
0x14001f8b9  mov     rbx, rcx
0x14001f8bc  jz      short loc_14001F8EF
0x14001f8be  mov     rcx, [rcx+8]
0x14001f8c2  xor     r8d, r8d
0x14001f8c5  xor     edx, edx
0x14001f8c7  call    WinHvSetInterceptRoutine
0x14001f8cc  test    eax, eax
0x14001f8ce  js      short loc_14001F908
0x14001f8d0  mov     rcx, [rbx+8]
0x14001f8d4  xor     r8d, r8d
0x14001f8d7  xor     edx, edx
0x14001f8d9  call    WinHvSetLowMemoryPolicyRoutine
0x14001f8de  test    eax, eax
0x14001f8e0  js      short loc_14001F908
0x14001f8e2  mov     rcx, [rbx+8]
0x14001f8e6  mov     dl, 1
0x14001f8e8  call    WinHvpDeleteWinHvPartition
0x14001f8ed  jmp     short loc_14001F908
0x14001f8ef  mov     rdx, [rcx+10h]
0x14001f8f3  test    rdx, rdx
0x14001f8f6  jz      short loc_14001F903
0x14001f8f8  mov     rcx, [rcx+8]
0x14001f8fc  call    WinHvpDeletePartition
0x14001f901  jmp     short loc_14001F908
0x14001f903  mov     eax, 0C000000Dh
0x14001f908  add     rsp, 20h
0x14001f90c  pop     rbx
0x14001f90d  retn
```
