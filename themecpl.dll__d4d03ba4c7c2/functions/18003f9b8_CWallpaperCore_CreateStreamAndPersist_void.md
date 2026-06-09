# CWallpaperCore::_CreateStreamAndPersist(void)

- ea: `0x18003f9b8`
- end: `0x18003fac1`
- name: `?_CreateStreamAndPersist@CWallpaperCore@@AEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004289c`

## callees

- `0x18003f9b8`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18003fa33`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18003fa33`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003fa91`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003fa91`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003fa5d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003fa5d`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_CreateStreamAndPersist(CWallpaperCore *this)
{
  HRESULT StreamOnHGlobal; // ebx
  HGLOBAL v3; // rax
  void *v4; // rdi
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  SIZE_T dwBytes; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  StreamOnHGlobal = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 52))(
                      *((_QWORD *)this + 52),
                      &GUID_00000109_0000_0000_c000_000000000046,
                      &v6);
  if ( StreamOnHGlobal >= 0 )
  {
    dwBytes = 0;
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, SIZE_T *))(*(_QWORD *)v6 + 56LL))(v6, &dwBytes);
    if ( StreamOnHGlobal >= 0 )
    {
      if ( HIDWORD(dwBytes) )
      {
        StreamOnHGlobal = -2147467259;
      }
      else
      {
        v3 = GlobalAlloc(0, (unsigned int)dwBytes);
        v4 = v3;
        if ( v3 )
        {
          StreamOnHGlobal = CreateStreamOnHGlobal(v3, 1, (LPSTREAM *)this + 53);
          if ( StreamOnHGlobal < 0 )
            GlobalFree(v4);
          else
            StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 48LL))(
                                v6,
                                *((_QWORD *)this + 53),
                                0);
        }
        else
        {
          StreamOnHGlobal = -2147024882;
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18003f9b8  mov     r11, rsp
0x18003f9bb  mov     [r11+18h], rbx
0x18003f9bf  mov     [r11+20h], rsi
0x18003f9c3  push    rdi
0x18003f9c4  sub     rsp, 20h
0x18003f9c8  mov     rsi, rcx
0x18003f9cb  mov     qword ptr [r11+8], 0
0x18003f9d3  mov     rcx, [rcx+1A0h]
0x18003f9da  lea     r8, [r11+8]
0x18003f9de  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18003f9e5  mov     rax, [rcx]
0x18003f9e8  mov     rax, [rax]
0x18003f9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9f0  mov     ebx, eax
0x18003f9f2  test    eax, eax
0x18003f9f4  js      loc_18003FAAE
0x18003f9fa  mov     rcx, [rsp+28h+arg_0]
0x18003f9ff  lea     rdx, [rsp+28h+dwBytes]
0x18003fa04  mov     [rsp+28h+dwBytes], 0
0x18003fa0d  mov     rax, [rcx]
0x18003fa10  mov     rax, [rax+38h]
0x18003fa14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa19  mov     ebx, eax
0x18003fa1b  test    eax, eax
0x18003fa1d  js      short loc_18003FA9D
0x18003fa1f  cmp     dword ptr [rsp+28h+dwBytes+4], 0
0x18003fa24  jz      short loc_18003FA2D
0x18003fa26  mov     ebx, 80004005h
0x18003fa2b  jmp     short loc_18003FA9D
0x18003fa2d  mov     edx, dword ptr [rsp+28h+dwBytes]; dwBytes
0x18003fa31  xor     ecx, ecx; uFlags
0x18003fa33  call    cs:__imp_GlobalAlloc
0x18003fa3a  nop     dword ptr [rax+rax+00h]
0x18003fa3f  mov     rdi, rax
0x18003fa42  test    rax, rax
0x18003fa45  jnz     short loc_18003FA4E
0x18003fa47  mov     ebx, 8007000Eh
0x18003fa4c  jmp     short loc_18003FA9D
0x18003fa4e  lea     r8, [rsi+1A8h]; ppstm
0x18003fa55  mov     edx, 1; fDeleteOnRelease
0x18003fa5a  mov     rcx, rdi; hGlobal
0x18003fa5d  call    cs:__imp_CreateStreamOnHGlobal
0x18003fa64  nop     dword ptr [rax+rax+00h]
0x18003fa69  mov     ebx, eax
0x18003fa6b  test    eax, eax
0x18003fa6d  js      short loc_18003FA8E
0x18003fa6f  mov     rcx, [rsp+28h+arg_0]
0x18003fa74  xor     r8d, r8d
0x18003fa77  mov     rdx, [rsi+1A8h]
0x18003fa7e  mov     rax, [rcx]
0x18003fa81  mov     rax, [rax+30h]
0x18003fa85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa8a  mov     ebx, eax
0x18003fa8c  jmp     short loc_18003FA9D
0x18003fa8e  mov     rcx, rdi; hMem
0x18003fa91  call    cs:__imp_GlobalFree
0x18003fa98  nop     dword ptr [rax+rax+00h]
0x18003fa9d  mov     rcx, [rsp+28h+arg_0]
0x18003faa2  mov     rax, [rcx]
0x18003faa5  mov     rax, [rax+10h]
0x18003faa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003faae  mov     rsi, [rsp+28h+arg_18]
0x18003fab3  mov     eax, ebx
0x18003fab5  mov     rbx, [rsp+28h+arg_10]
0x18003faba  add     rsp, 20h
0x18003fabe  pop     rdi
0x18003fabf  retn
```
