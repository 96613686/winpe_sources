# FilterRemoveAllVirtualAdapters

- ea: `0x14000448c`
- end: `0x140004561`
- name: `FilterRemoveAllVirtualAdapters`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400041a0`
- `0x14000c5b0`

## callees

- `0x14000448c`
- `0x140004568`
- `0x14000d8ec`
- `0x14000d91c`

## pseudocode

```c
__int64 __fastcall FilterRemoveAllVirtualAdapters(__int64 a1)
{
  unsigned int v2; // ebx
  unsigned int i; // edi

  v2 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  for ( i = 1; i < *(_DWORD *)(a1 + 2684); ++i )
  {
    v2 = FilterSetVirtualAdapter(a1, i, 0);
    if ( v2
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x14000448c  push    rbx
0x14000448e  push    rsi
0x14000448f  push    rdi
0x140004490  push    r14
0x140004492  sub     rsp, 28h
0x140004496  mov     rsi, rcx
0x140004499  xor     ebx, ebx
0x14000449b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044a2  lea     r14, WPP_GLOBAL_Control
0x1400044a9  cmp     rcx, r14
0x1400044ac  jnz     short loc_14000451F
0x1400044ae  mov     edi, 1
0x1400044b3  cmp     [rsi+0A7Ch], edi
0x1400044b9  jbe     short loc_1400044D8
0x1400044bb  xor     r8d, r8d
0x1400044be  mov     edx, edi
0x1400044c0  mov     rcx, rsi
0x1400044c3  call    FilterSetVirtualAdapter
0x1400044c8  mov     ebx, eax
0x1400044ca  test    eax, eax
0x1400044cc  jnz     short loc_1400044F1
0x1400044ce  inc     edi
0x1400044d0  cmp     edi, [rsi+0A7Ch]
0x1400044d6  jb      short loc_1400044BB
0x1400044d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044df  cmp     rcx, r14
0x1400044e2  jnz     short loc_140004540
0x1400044e4  mov     eax, ebx
0x1400044e6  add     rsp, 28h
0x1400044ea  pop     r14
0x1400044ec  pop     rdi
0x1400044ed  pop     rsi
0x1400044ee  pop     rbx
0x1400044ef  retn
0x1400044f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044f8  cmp     rcx, r14
0x1400044fb  jz      short loc_1400044CE
0x1400044fd  mov     edx, [rcx+2Ch]
0x140004500  test    dl, 1
0x140004503  jz      short loc_1400044CE
0x140004505  mov     rcx, [rcx+18h]
0x140004509  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140004510  mov     edx, 47h ; 'G'
0x140004515  mov     r9d, eax
0x140004518  call    WPP_SF_d
0x14000451d  jmp     short loc_1400044CE
0x14000451f  mov     eax, [rcx+2Ch]
0x140004522  test    al, 20h
0x140004524  jz      short loc_1400044AE
0x140004526  mov     rcx, [rcx+18h]
0x14000452a  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140004531  mov     edx, 46h ; 'F'
0x140004536  call    WPP_SF_
0x14000453b  jmp     loc_1400044AE
0x140004540  mov     eax, [rcx+2Ch]
0x140004543  test    al, 20h
0x140004545  jz      short loc_1400044E4
0x140004547  mov     rcx, [rcx+18h]
0x14000454b  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140004552  mov     edx, 48h ; 'H'
0x140004557  mov     r9d, ebx
0x14000455a  call    WPP_SF_d
0x14000455f  jmp     short loc_1400044E4
```
