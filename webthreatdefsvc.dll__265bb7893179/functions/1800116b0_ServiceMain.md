# ServiceMain

- ea: `0x1800116b0`
- end: `0x180011789`
- name: `ServiceMain`
- size: `217`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001500`
- `0x1800016a0`
- `0x180010430`
- `0x1800116b0`
- `0x180013b0c`

## string_xrefs

- `0x1800116e0`: `ServiceMain Enter`
- `0x18001174a`: `ServiceMain Exit`

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

  v0 = qword_1800268D8;
  if ( *(_DWORD *)qword_1800268D8 > 5u && (unsigned __int8)sub_1800016A0(qword_1800268D8, 4096) )
  {
    v8 = L"WebThreatDefSvc";
    v9 = "ServiceMain Enter";
    sub_180001500(v0, (unsigned int)&dword_180021414, v1, v2, (__int64)&v9, (__int64)&v8);
  }
  v3 = sub_180010430();
  if ( v3 < 0 )
  {
    LODWORD(v8) = v3;
    sub_180013B0C(&v8);
  }
  v4 = qword_1800268D8;
  result = *(unsigned int *)qword_1800268D8;
  if ( (unsigned int)result > 5 )
  {
    result = sub_1800016A0(qword_1800268D8, 4096);
    if ( (_BYTE)result )
    {
      v8 = L"WebThreatDefSvc";
      v9 = "ServiceMain Exit";
      return sub_180001500(v4, (unsigned int)byte_1800213EB, v6, v7, (__int64)&v9, (__int64)&v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800116b0  mov     [rsp+arg_0], rbx
0x1800116b5  push    rsi
0x1800116b6  sub     rsp, 30h
0x1800116ba  mov     rbx, cs:qword_1800268D8
0x1800116c1  lea     rsi, ServiceName; "WebThreatDefSvc"
0x1800116c8  mov     eax, [rbx]
0x1800116ca  cmp     eax, 5
0x1800116cd  jbe     short loc_180011714
0x1800116cf  mov     edx, 1000h
0x1800116d4  mov     rcx, rbx
0x1800116d7  call    sub_1800016A0
0x1800116dc  test    al, al
0x1800116de  jz      short loc_180011714
0x1800116e0  lea     rax, aServicemainEnt; "ServiceMain Enter"
0x1800116e7  mov     [rsp+38h+arg_10], rsi
0x1800116ec  mov     [rsp+38h+arg_18], rax
0x1800116f1  lea     rdx, dword_180021414
0x1800116f8  lea     rax, [rsp+38h+arg_10]
0x1800116fd  mov     rcx, rbx
0x180011700  mov     [rsp+38h+var_10], rax
0x180011705  lea     rax, [rsp+38h+arg_18]
0x18001170a  mov     [rsp+38h+var_18], rax
0x18001170f  call    sub_180001500
0x180011714  call    sub_180010430
0x180011719  test    eax, eax
0x18001171b  jns     short loc_18001172B
0x18001171d  lea     rcx, [rsp+38h+arg_10]
0x180011722  mov     dword ptr [rsp+38h+arg_10], eax
0x180011726  call    sub_180013B0C
0x18001172b  mov     rbx, cs:qword_1800268D8
0x180011732  mov     eax, [rbx]
0x180011734  cmp     eax, 5
0x180011737  jbe     short loc_18001177E
0x180011739  mov     edx, 1000h
0x18001173e  mov     rcx, rbx
0x180011741  call    sub_1800016A0
0x180011746  test    al, al
0x180011748  jz      short loc_18001177E
0x18001174a  lea     rax, aServicemainExi; "ServiceMain Exit"
0x180011751  mov     [rsp+38h+arg_10], rsi
0x180011756  mov     [rsp+38h+arg_18], rax
0x18001175b  lea     rdx, byte_1800213EB
0x180011762  lea     rax, [rsp+38h+arg_10]
0x180011767  mov     rcx, rbx
0x18001176a  mov     [rsp+38h+var_10], rax
0x18001176f  lea     rax, [rsp+38h+arg_18]
0x180011774  mov     [rsp+38h+var_18], rax
0x180011779  call    sub_180001500
0x18001177e  mov     rbx, [rsp+38h+arg_0]
0x180011783  add     rsp, 30h
0x180011787  pop     rsi
0x180011788  retn
```
