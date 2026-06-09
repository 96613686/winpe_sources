# NotificationParser::~NotificationParser(void)

- ea: `0x180014074`
- end: `0x1800140ed`
- name: `??1NotificationParser@@QEAA@XZ`
- size: `121`
- prototype: `void __fastcall(NotificationParser *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030a30`

## callees

- `0x180014074`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014081`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NotificationParser::~NotificationParser(HSTRING *this)
{
  HSTRING v2; // rcx
  HSTRING v3; // rcx
  HSTRING v4; // rcx

  WindowsDeleteString(this[3]);
  this[3] = 0;
  v2 = this[2];
  if ( v2 )
  {
    this[2] = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = this[1];
  if ( v3 )
  {
    this[1] = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *this;
  if ( *this )
  {
    *this = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x180014074  push    rbx
0x180014076  sub     rsp, 20h
0x18001407a  mov     rbx, rcx
0x18001407d  mov     rcx, [rcx+18h]; string
0x180014081  call    cs:__imp_WindowsDeleteString
0x180014087  mov     qword ptr [rbx+18h], 0
0x18001408f  mov     rcx, [rbx+10h]
0x180014093  test    rcx, rcx
0x180014096  jz      short loc_1800140AD
0x180014098  mov     qword ptr [rbx+10h], 0
0x1800140a0  mov     rax, [rcx]
0x1800140a3  mov     rax, [rax+10h]
0x1800140a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140ac  nop
0x1800140ad  mov     rcx, [rbx+8]
0x1800140b1  test    rcx, rcx
0x1800140b4  jz      short loc_1800140CB
0x1800140b6  mov     qword ptr [rbx+8], 0
0x1800140be  mov     rax, [rcx]
0x1800140c1  mov     rax, [rax+10h]
0x1800140c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140ca  nop
0x1800140cb  mov     rcx, [rbx]
0x1800140ce  test    rcx, rcx
0x1800140d1  jz      short loc_1800140E7
0x1800140d3  mov     qword ptr [rbx], 0
0x1800140da  mov     rax, [rcx]
0x1800140dd  mov     rax, [rax+10h]
0x1800140e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140e6  nop
0x1800140e7  add     rsp, 20h
0x1800140eb  pop     rbx
0x1800140ec  retn
```
