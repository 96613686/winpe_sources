# PROTOCOL_HANDLE_OBJECT::~PROTOCOL_HANDLE_OBJECT(void)

- ea: `0x1800b11f4`
- end: `0x1800b1278`
- name: `??1PROTOCOL_HANDLE_OBJECT@@UEAA@XZ`
- size: `132`
- prototype: `void __fastcall(PROTOCOL_HANDLE_OBJECT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b1280`

## callees

- `0x18001b4d0`
- `0x1800b11f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b1265`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b1265`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b124d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b124d`
- `webio!__imp_WebCloseProtocolHandle` at `0x1800b1213`
- `webio!__imp_WebCloseProtocolHandle` at `0x1800b1213`

## pseudocode

```c
void __fastcall PROTOCOL_HANDLE_OBJECT::~PROTOCOL_HANDLE_OBJECT(PROTOCOL_HANDLE_OBJECT *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &PROTOCOL_HANDLE_OBJECT::`vftable';
  if ( *((_QWORD *)this + 54) )
  {
    WebCloseProtocolHandle();
    *((_QWORD *)this + 54) = 0;
  }
  v2 = (void *)*((_QWORD *)this + 59);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 59) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 56);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 56) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  INTERNET_CONNECT_HANDLE_OBJECT::~INTERNET_CONNECT_HANDLE_OBJECT(this);
}

```

## disassembly

```asm
0x1800b11f4  push    rbx
0x1800b11f6  sub     rsp, 20h
0x1800b11fa  lea     rax, ??_7PROTOCOL_HANDLE_OBJECT@@6B@; const PROTOCOL_HANDLE_OBJECT::`vftable'
0x1800b1201  mov     rbx, rcx
0x1800b1204  mov     [rcx], rax
0x1800b1207  mov     rcx, [rcx+1B0h]
0x1800b120e  test    rcx, rcx
0x1800b1211  jz      short loc_1800B1224
0x1800b1213  call    cs:__imp_WebCloseProtocolHandle
0x1800b1219  mov     qword ptr [rbx+1B0h], 0
0x1800b1224  mov     rcx, [rbx+1D8h]; hObject
0x1800b122b  test    rcx, rcx
0x1800b122e  jz      short loc_1800B1241
0x1800b1230  call    cs:__imp_CloseHandle
0x1800b1236  mov     qword ptr [rbx+1D8h], 0
0x1800b1241  mov     rcx, [rbx+1C0h]; hObject
0x1800b1248  test    rcx, rcx
0x1800b124b  jz      short loc_1800B125E
0x1800b124d  call    cs:__imp_CloseHandle
0x1800b1253  mov     qword ptr [rbx+1C0h], 0
0x1800b125e  lea     rcx, [rbx+1E8h]; lpCriticalSection
0x1800b1265  call    cs:__imp_DeleteCriticalSection
0x1800b126b  mov     rcx, rbx; this
0x1800b126e  add     rsp, 20h
0x1800b1272  pop     rbx
0x1800b1273  jmp     ??1INTERNET_CONNECT_HANDLE_OBJECT@@UEAA@XZ; INTERNET_CONNECT_HANDLE_OBJECT::~INTERNET_CONNECT_HANDLE_OBJECT(void)
```
