# ServiceMain

- ea: `0x180021b10`
- end: `0x180021be9`
- name: `ServiceMain`
- size: `217`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180002244`
- `0x1800023e4`
- `0x18002089c`
- `0x180021b10`
- `0x180024e88`

## string_xrefs

- `0x180021b40`: `ServiceMain Enter`
- `0x180021baa`: `ServiceMain Exit`

## pseudocode

```c
__int64 ServiceMain()
{
  int v0; // ebx
  int v1; // r8d
  int v2; // r9d
  int v3; // eax
  int v4; // ebx
  __int64 result; // rax
  int v6; // r8d
  int v7; // r9d
  const WCHAR *v8; // [rsp+50h] [rbp+18h] BYREF
  const char *v9; // [rsp+58h] [rbp+20h] BYREF

  v0 = qword_180040EC0;
  if ( *(_DWORD *)qword_180040EC0 > 5u && (unsigned __int8)sub_1800023E4(qword_180040EC0, 4096) )
  {
    v8 = L"WebThreatDefUserSvc";
    v9 = "ServiceMain Enter";
    sub_180002244(v0, (unsigned int)byte_180037C81, v1, v2, (__int64)&v9, (__int64)&v8);
  }
  v3 = sub_18002089C();
  if ( v3 < 0 )
  {
    LODWORD(v8) = v3;
    sub_180024E88(&v8);
  }
  v4 = qword_180040EC0;
  result = *(unsigned int *)qword_180040EC0;
  if ( (unsigned int)result > 5 )
  {
    result = sub_1800023E4(qword_180040EC0, 4096);
    if ( (_BYTE)result )
    {
      v8 = L"WebThreatDefUserSvc";
      v9 = "ServiceMain Exit";
      return sub_180002244(v4, (unsigned int)qword_180037C58, v6, v7, (__int64)&v9, (__int64)&v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021b10  mov     [rsp+arg_0], rbx
0x180021b15  push    rsi
0x180021b16  sub     rsp, 30h
0x180021b1a  mov     rbx, cs:qword_180040EC0
0x180021b21  lea     rsi, ServiceName; "WebThreatDefUserSvc"
0x180021b28  mov     eax, [rbx]
0x180021b2a  cmp     eax, 5
0x180021b2d  jbe     short loc_180021B74
0x180021b2f  mov     edx, 1000h
0x180021b34  mov     rcx, rbx
0x180021b37  call    sub_1800023E4
0x180021b3c  test    al, al
0x180021b3e  jz      short loc_180021B74
0x180021b40  lea     rax, aServicemainEnt; "ServiceMain Enter"
0x180021b47  mov     [rsp+38h+arg_10], rsi
0x180021b4c  mov     [rsp+38h+arg_18], rax
0x180021b51  lea     rdx, byte_180037C81
0x180021b58  lea     rax, [rsp+38h+arg_10]
0x180021b5d  mov     rcx, rbx
0x180021b60  mov     [rsp+38h+var_10], rax
0x180021b65  lea     rax, [rsp+38h+arg_18]
0x180021b6a  mov     [rsp+38h+var_18], rax
0x180021b6f  call    sub_180002244
0x180021b74  call    sub_18002089C
0x180021b79  test    eax, eax
0x180021b7b  jns     short loc_180021B8B
0x180021b7d  lea     rcx, [rsp+38h+arg_10]
0x180021b82  mov     dword ptr [rsp+38h+arg_10], eax
0x180021b86  call    sub_180024E88
0x180021b8b  mov     rbx, cs:qword_180040EC0
0x180021b92  mov     eax, [rbx]
0x180021b94  cmp     eax, 5
0x180021b97  jbe     short loc_180021BDE
0x180021b99  mov     edx, 1000h
0x180021b9e  mov     rcx, rbx
0x180021ba1  call    sub_1800023E4
0x180021ba6  test    al, al
0x180021ba8  jz      short loc_180021BDE
0x180021baa  lea     rax, aServicemainExi; "ServiceMain Exit"
0x180021bb1  mov     [rsp+38h+arg_10], rsi
0x180021bb6  mov     [rsp+38h+arg_18], rax
0x180021bbb  lea     rdx, qword_180037C58
0x180021bc2  lea     rax, [rsp+38h+arg_10]
0x180021bc7  mov     rcx, rbx
0x180021bca  mov     [rsp+38h+var_10], rax
0x180021bcf  lea     rax, [rsp+38h+arg_18]
0x180021bd4  mov     [rsp+38h+var_18], rax
0x180021bd9  call    sub_180002244
0x180021bde  mov     rbx, [rsp+38h+arg_0]
0x180021be3  add     rsp, 30h
0x180021be7  pop     rsi
0x180021be8  retn
```
