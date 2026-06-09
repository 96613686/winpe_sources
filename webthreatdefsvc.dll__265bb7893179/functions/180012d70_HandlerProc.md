# HandlerProc

- ea: `0x180012d70`
- end: `0x180012dda`
- name: `HandlerProc`
- size: `106`
- prototype: `__int64 __fastcall(__int64 dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180001010`
- `0x180001690`
- `0x1800016a0`
- `0x180012814`
- `0x180012900`
- `0x180012d70`

## string_xrefs

- `0x180012da9`: `Service: null context received from SCM for ServiceControlHandler.`

## pseudocode

```c
__int64 __fastcall HandlerProc(__int64 dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  int v5; // ebx
  __int64 v6; // rax
  char v7; // [rsp+58h] [rbp+20h] BYREF

  if ( !lpContext )
  {
    v5 = qword_1800268D8;
    if ( *(_DWORD *)qword_1800268D8 > 2u && (unsigned __int8)sub_1800016A0(qword_1800268D8, 4096) )
    {
      v6 = sub_180001690(&v7, "Service: null context received from SCM for ServiceControlHandler.");
      sub_180001010(v5, (unsigned int)byte_1800215B1, 0, 0, v6);
    }
    sub_180012814(dwControl, dwEventType, lpEventData);
  }
  return sub_180012900(lpContext, (unsigned int)dwControl, lpEventData);
}

```

## disassembly

```asm
0x180012d70  push    rbx
0x180012d72  sub     rsp, 30h
0x180012d76  test    r9, r9
0x180012d79  jz      short loc_180012D8A
0x180012d7b  mov     edx, ecx
0x180012d7d  mov     rcx, r9
0x180012d80  add     rsp, 30h
0x180012d84  pop     rbx
0x180012d85  jmp     sub_180012900
0x180012d8a  mov     rbx, cs:qword_1800268D8
0x180012d91  mov     eax, [rbx]
0x180012d93  cmp     eax, 2
0x180012d96  jbe     short loc_180012DD4
0x180012d98  mov     edx, 1000h
0x180012d9d  mov     rcx, rbx
0x180012da0  call    sub_1800016A0
0x180012da5  test    al, al
0x180012da7  jz      short loc_180012DD4
0x180012da9  lea     rdx, aServiceNullCon; "Service: null context received from SCM"...
0x180012db0  lea     rcx, [rsp+38h+arg_18]
0x180012db5  call    sub_180001690
0x180012dba  xor     r9d, r9d
0x180012dbd  mov     [rsp+38h+var_18], rax
0x180012dc2  xor     r8d, r8d
0x180012dc5  lea     rdx, byte_1800215B1
0x180012dcc  mov     rcx, rbx
0x180012dcf  call    sub_180001010
0x180012dd4  call    sub_180012814
```
