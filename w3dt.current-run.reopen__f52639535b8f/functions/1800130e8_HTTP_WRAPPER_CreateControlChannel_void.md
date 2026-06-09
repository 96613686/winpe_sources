# HTTP_WRAPPER::CreateControlChannel(void)

- ea: `0x1800130e8`
- end: `0x180013139`
- name: `?CreateControlChannel@HTTP_WRAPPER@@QEAAKXZ`
- size: `81`
- prototype: `unsigned int __fastcall(HTTP_WRAPPER *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180012530`
- `0x1800143dc`

## callees

- `0x1800130e8`
- `0x180013140`
- `0x180013170`

## import_xrefs

- `HTTPAPI!HttpCreateServerSession` at `0x180013108`
- `HTTPAPI!HttpCreateServerSession` at `0x180013108`

## pseudocode

```c
__int64 __fastcall HTTP_WRAPPER::CreateControlChannel(HTTP_OPAQUE_ID *this)
{
  ULONG ServerSession; // ebx

  ServerSession = HttpCreateServerSession((HTTPAPI_VERSION)2, this + 2, 0);
  if ( ServerSession || (ServerSession = HTTP_WRAPPER::SetControlChannelStateInternal((HTTP_WRAPPER *)this, 0)) != 0 )
    HTTP_WRAPPER::CloseControlChannel((HTTP_WRAPPER *)this);
  return ServerSession;
}

```

## disassembly

```asm
0x1800130e8  mov     [rsp+arg_8], rbx
0x1800130ed  push    rdi
0x1800130ee  sub     rsp, 20h
0x1800130f2  mov     rdi, rcx
0x1800130f5  mov     dword ptr [rsp+28h+Version.HttpApiMajorVersion], 2
0x1800130fd  lea     rdx, [rcx+10h]; ServerSessionId
0x180013101  xor     r8d, r8d; Reserved
0x180013104  mov     ecx, dword ptr [rsp+28h+Version.HttpApiMajorVersion]; Version
0x180013108  call    cs:__imp_HttpCreateServerSession
0x18001310e  mov     ebx, eax
0x180013110  test    eax, eax
0x180013112  jnz     short loc_180013124
0x180013114  xor     edx, edx; int
0x180013116  mov     rcx, rdi; this
0x180013119  call    ?SetControlChannelStateInternal@HTTP_WRAPPER@@AEAAKH@Z; HTTP_WRAPPER::SetControlChannelStateInternal(int)
0x18001311e  mov     ebx, eax
0x180013120  test    eax, eax
0x180013122  jz      short loc_18001312C
0x180013124  mov     rcx, rdi; this
0x180013127  call    ?CloseControlChannel@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::CloseControlChannel(void)
0x18001312c  mov     eax, ebx
0x18001312e  mov     rbx, [rsp+28h+arg_8]
0x180013133  add     rsp, 20h
0x180013137  pop     rdi
0x180013138  retn
```
