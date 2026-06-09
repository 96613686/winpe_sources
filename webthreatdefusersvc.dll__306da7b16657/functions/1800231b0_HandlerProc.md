# HandlerProc

- ea: `0x1800231b0`
- end: `0x18002321a`
- name: `HandlerProc`
- size: `106`
- prototype: `__int64 __fastcall(__int64 dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180001010`
- `0x1800023d4`
- `0x1800023e4`
- `0x180022c0c`
- `0x180022cf8`
- `0x1800231b0`

## string_xrefs

- `0x1800231e9`: `Service: null context received from SCM for ServiceControlHandler.`

## pseudocode

```c
__int64 __fastcall HandlerProc(__int64 dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  int v5; // ebx
  __int64 v6; // rax
  char v7; // [rsp+58h] [rbp+20h] BYREF

  if ( !lpContext )
  {
    v5 = qword_180040EC0;
    if ( *(_DWORD *)qword_180040EC0 > 2u && (unsigned __int8)sub_1800023E4(qword_180040EC0, 4096) )
    {
      v6 = sub_1800023D4(&v7, "Service: null context received from SCM for ServiceControlHandler.");
      sub_180001010(v5, (unsigned int)&word_180037E1E, 0, 0, v6);
    }
    sub_180022C0C(dwControl, dwEventType, lpEventData);
  }
  return sub_180022CF8(lpContext, (unsigned int)dwControl, lpEventData);
}

```

## disassembly

```asm
0x1800231b0  push    rbx
0x1800231b2  sub     rsp, 30h
0x1800231b6  test    r9, r9
0x1800231b9  jz      short loc_1800231CA
0x1800231bb  mov     edx, ecx
0x1800231bd  mov     rcx, r9
0x1800231c0  add     rsp, 30h
0x1800231c4  pop     rbx
0x1800231c5  jmp     sub_180022CF8
0x1800231ca  mov     rbx, cs:qword_180040EC0
0x1800231d1  mov     eax, [rbx]
0x1800231d3  cmp     eax, 2
0x1800231d6  jbe     short loc_180023214
0x1800231d8  mov     edx, 1000h
0x1800231dd  mov     rcx, rbx
0x1800231e0  call    sub_1800023E4
0x1800231e5  test    al, al
0x1800231e7  jz      short loc_180023214
0x1800231e9  lea     rdx, aServiceNullCon; "Service: null context received from SCM"...
0x1800231f0  lea     rcx, [rsp+38h+arg_18]
0x1800231f5  call    sub_1800023D4
0x1800231fa  xor     r9d, r9d
0x1800231fd  mov     [rsp+38h+var_18], rax
0x180023202  xor     r8d, r8d
0x180023205  lea     rdx, word_180037E1E
0x18002320c  mov     rcx, rbx
0x18002320f  call    sub_180001010
0x180023214  call    sub_180022C0C
```
