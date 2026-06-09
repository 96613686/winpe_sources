# AdjustThreadTime

- ea: `0x140002c20`
- end: `0x140002d92`
- name: `AdjustThreadTime`
- size: `370`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400033c0`
- `0x140003a30`
- `0x140006588`
- `0x1400069c8`
- `0x1400078ec`
- `0x140009d78`
- `0x140009ea8`
- `0x14000a0d4`

## callees

- `0x140002c20`
- `0x140004778`

## pseudocode

```c
__int64 __fastcall AdjustThreadTime(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // rax
  unsigned int v6; // eax
  unsigned __int64 v7; // rax
  unsigned int v8; // eax

  result = *(_QWORD *)(a1 + 24);
  if ( result != *(_QWORD *)&EventTraceGuid.Data1
    || (result = *(_QWORD *)(a1 + 32), result != *(_QWORD *)EventTraceGuid.Data4) )
  {
    if ( a2 && !*(_DWORD *)(a2 + 108) )
    {
      if ( *((_BYTE *)g_TraceContext + 8505) )
      {
        GetEventCategory((struct _EVENT_RECORD *)a1);
        v5 = *(_QWORD *)(a1 + 16);
        *(_QWORD *)(a2 + 176) = v5;
        if ( v5 > *(_QWORD *)&SystemTimeAsFileTime )
          *(struct _FILETIME *)(a2 + 176) = SystemTimeAsFileTime;
        v6 = *(_DWORD *)(a1 + 56);
        if ( *(_DWORD *)(a2 + 188) < v6 )
          *(_DWORD *)(a2 + 188) = v6;
        result = *(unsigned int *)(a1 + 60);
        if ( *(_DWORD *)(a2 + 196) < (unsigned int)result )
          *(_DWORD *)(a2 + 196) = result;
      }
      else
      {
        v7 = *(_QWORD *)(a1 + 16);
        *(_QWORD *)(a2 + 176) = v7;
        if ( v7 > *(_QWORD *)&SystemTimeAsFileTime )
          *(struct _FILETIME *)(a2 + 176) = SystemTimeAsFileTime;
        v8 = *(_DWORD *)(a1 + 56);
        if ( *(_DWORD *)(a2 + 188) < v8 )
          *(_DWORD *)(a2 + 188) = v8;
        result = *(unsigned int *)(a1 + 60);
        if ( *(_DWORD *)(a2 + 196) < (unsigned int)result )
          *(_DWORD *)(a2 + 196) = result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002c20  mov     [rsp+arg_8], rbx
0x140002c25  push    rdi
0x140002c26  sub     rsp, 20h
0x140002c2a  mov     rax, [rcx+18h]
0x140002c2e  mov     rbx, rdx
0x140002c31  cmp     rax, qword ptr cs:EventTraceGuid.Data1
0x140002c38  mov     rdi, rcx
0x140002c3b  mov     [rsp+28h+arg_10], 0
0x140002c43  mov     [rsp+28h+arg_0], 0
0x140002c4b  jnz     short loc_140002C5E
0x140002c4d  mov     rax, [rcx+20h]
0x140002c51  cmp     rax, qword ptr cs:EventTraceGuid.Data4
0x140002c58  jz      loc_140002D87
0x140002c5e  test    rbx, rbx
0x140002c61  jz      loc_140002D87
0x140002c67  cmp     dword ptr [rdx+6Ch], 0
0x140002c6b  jnz     loc_140002D87
0x140002c71  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140002c78  cmp     byte ptr [rax+2139h], 0
0x140002c7f  jz      loc_140002D47
0x140002c85  lea     r8, [rsp+28h+arg_0]
0x140002c8a  lea     rdx, [rsp+28h+arg_10]
0x140002c8f  call    GetEventCategory
0x140002c94  mov     ecx, [rsp+28h+arg_0]
0x140002c98  test    ecx, ecx
0x140002c9a  jz      short loc_140002D05
0x140002c9c  sub     ecx, 1
0x140002c9f  jz      short loc_140002CD1
0x140002ca1  cmp     ecx, 1
0x140002ca4  jnz     loc_140002D87
0x140002caa  mov     rax, [rdi+10h]
0x140002cae  mov     [rbx+0B0h], rax
0x140002cb5  mov     rcx, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x140002cbc  cmp     rax, rcx
0x140002cbf  jbe     loc_140002D87
0x140002cc5  mov     [rbx+0B0h], rcx
0x140002ccc  jmp     loc_140002D87
0x140002cd1  mov     eax, [rdi+38h]
0x140002cd4  mov     [rbx+0B8h], eax
0x140002cda  mov     eax, [rdi+3Ch]
0x140002cdd  mov     [rbx+0C0h], eax
0x140002ce3  mov     eax, [rdi+38h]
0x140002ce6  mov     [rbx+0BCh], eax
0x140002cec  mov     eax, [rdi+3Ch]
0x140002cef  mov     [rbx+0C4h], eax
0x140002cf5  mov     rax, [rdi+10h]
0x140002cf9  mov     [rbx+0B0h], rax
0x140002d00  jmp     loc_140002D87
0x140002d05  mov     rax, [rdi+10h]
0x140002d09  mov     [rbx+0B0h], rax
0x140002d10  mov     rcx, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x140002d17  cmp     rax, rcx
0x140002d1a  jbe     short loc_140002D23
0x140002d1c  mov     [rbx+0B0h], rcx
0x140002d23  mov     eax, [rdi+38h]
0x140002d26  cmp     [rbx+0BCh], eax
0x140002d2c  jnb     short loc_140002D34
0x140002d2e  mov     [rbx+0BCh], eax
0x140002d34  mov     eax, [rdi+3Ch]
0x140002d37  cmp     [rbx+0C4h], eax
0x140002d3d  jnb     short loc_140002D87
0x140002d3f  mov     [rbx+0C4h], eax
0x140002d45  jmp     short loc_140002D87
0x140002d47  mov     rax, [rcx+10h]
0x140002d4b  mov     [rdx+0B0h], rax
0x140002d52  mov     rcx, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x140002d59  cmp     rax, rcx
0x140002d5c  jbe     short loc_140002D65
0x140002d5e  mov     [rdx+0B0h], rcx
0x140002d65  mov     eax, [rdi+38h]
0x140002d68  cmp     [rdx+0BCh], eax
0x140002d6e  jnb     short loc_140002D76
0x140002d70  mov     [rdx+0BCh], eax
0x140002d76  mov     eax, [rdi+3Ch]
0x140002d79  cmp     [rdx+0C4h], eax
0x140002d7f  jnb     short loc_140002D87
0x140002d81  mov     [rdx+0C4h], eax
0x140002d87  mov     rbx, [rsp+28h+arg_8]
0x140002d8c  add     rsp, 20h
0x140002d90  pop     rdi
0x140002d91  retn
```
