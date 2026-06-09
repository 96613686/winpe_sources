# UserScaleRgn

- ea: `0x180052d64`
- end: `0x180052e5d`
- name: `UserScaleRgn`
- size: `249`
- prototype: `__int64 __fastcall(HRGN hrgnDst)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18005d130`

## callees

- `0x180052d64`

## import_xrefs

- `win32u!NtUserTransformRect` at `0x180052df2`
- `win32u!NtUserTransformRect` at `0x180052df2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052da7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052da7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052e40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052e40`
- `GDI32!ExtCreateRegion` at `0x180052e0f`
- `GDI32!ExtCreateRegion` at `0x180052e0f`
- `GDI32!GetRegionData` at `0x180052d8d`
- `GDI32!GetRegionData` at `0x180052dc1`
- `GDI32!GetRegionData` at `0x180052d8d`
- `GDI32!GetRegionData` at `0x180052dc1`
- `GDI32!CombineRgn` at `0x180052e2c`
- `GDI32!CombineRgn` at `0x180052e2c`
- `GDI32!DeleteObject` at `0x180052e37`
- `GDI32!DeleteObject` at `0x180052e37`

## pseudocode

```c
__int64 __fastcall UserScaleRgn(HRGN hrgnDst, unsigned int a2, __int64 a3)
{
  unsigned int v4; // esi
  signed int RegionData; // eax
  DWORD v7; // edi
  struct _RGNDATA *v8; // rax
  RGNDATA *v9; // rbx
  int nCount; // r12d
  char *Buffer; // r14
  int v12; // r15d
  HRGN Region; // rax
  HRGN v14; // rdi

  v4 = 0;
  RegionData = GetRegionData(hrgnDst, 0, 0);
  v7 = RegionData;
  if ( RegionData )
  {
    v8 = (struct _RGNDATA *)LocalAlloc(0, 4LL * RegionData);
    v9 = v8;
    if ( v8 )
    {
      if ( GetRegionData(hrgnDst, v7, v8) )
      {
        nCount = v9->rdh.nCount;
        Buffer = v9->Buffer;
        v12 = 0;
        if ( nCount > 0 )
        {
          do
          {
            NtUserTransformRect(Buffer, a2, *(unsigned int *)(a3 + 288), *(_QWORD *)(a3 + 256));
            Buffer += 16;
            ++v12;
          }
          while ( v12 < nCount );
          v4 = 0;
        }
        Region = ExtCreateRegion(0, v7, v9);
        v14 = Region;
        if ( Region )
        {
          v4 = CombineRgn(hrgnDst, Region, 0, 5);
          DeleteObject(v14);
        }
      }
      LocalFree(v9);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180052d64  mov     [rsp+arg_0], rbx
0x180052d69  mov     [rsp+arg_8], edx
0x180052d6d  push    rbp
0x180052d6e  push    rsi
0x180052d6f  push    rdi
0x180052d70  push    r12
0x180052d72  push    r13
0x180052d74  push    r14
0x180052d76  push    r15
0x180052d78  sub     rsp, 20h
0x180052d7c  mov     r13, r8
0x180052d7f  xor     esi, esi
0x180052d81  xor     r8d, r8d; lpRgnData
0x180052d84  mov     [rsp+58h+arg_18], esi
0x180052d88  xor     edx, edx; nCount
0x180052d8a  mov     rbp, rcx
0x180052d8d  call    cs:__imp_GetRegionData
0x180052d93  movsxd  rdi, eax
0x180052d96  test    eax, eax
0x180052d98  jz      loc_180052E46
0x180052d9e  mov     rdx, rdi
0x180052da1  xor     ecx, ecx; uFlags
0x180052da3  shl     rdx, 2; uBytes
0x180052da7  call    cs:__imp_LocalAlloc
0x180052dad  mov     rbx, rax
0x180052db0  test    rax, rax
0x180052db3  jz      loc_180052E46
0x180052db9  mov     r8, rax; lpRgnData
0x180052dbc  mov     edx, edi; nCount
0x180052dbe  mov     rcx, rbp; hrgn
0x180052dc1  call    cs:__imp_GetRegionData
0x180052dc7  test    eax, eax
0x180052dc9  jz      short loc_180052E3D
0x180052dcb  mov     r12d, [rbx+8]
0x180052dcf  lea     r14, [rbx+20h]
0x180052dd3  xor     r15d, r15d
0x180052dd6  test    r12d, r12d
0x180052dd9  jle     short loc_180052E08
0x180052ddb  mov     esi, [rsp+58h+arg_8]
0x180052ddf  mov     r9, [r13+100h]
0x180052de6  mov     edx, esi
0x180052de8  mov     r8d, [r13+120h]
0x180052def  mov     rcx, r14
0x180052df2  call    cs:__imp_NtUserTransformRect
0x180052df8  add     r14, 10h
0x180052dfc  inc     r15d
0x180052dff  cmp     r15d, r12d
0x180052e02  jl      short loc_180052DDF
0x180052e04  mov     esi, [rsp+58h+arg_18]
0x180052e08  mov     r8, rbx; lpData
0x180052e0b  mov     edx, edi; nCount
0x180052e0d  xor     ecx, ecx; lpx
0x180052e0f  call    cs:__imp_ExtCreateRegion
0x180052e15  mov     rdi, rax
0x180052e18  test    rax, rax
0x180052e1b  jz      short loc_180052E3D
0x180052e1d  mov     r9d, 5; iMode
0x180052e23  xor     r8d, r8d; hrgnSrc2
0x180052e26  mov     rdx, rax; hrgnSrc1
0x180052e29  mov     rcx, rbp; hrgnDst
0x180052e2c  call    cs:__imp_CombineRgn
0x180052e32  mov     rcx, rdi; ho
0x180052e35  mov     esi, eax
0x180052e37  call    cs:__imp_DeleteObject
0x180052e3d  mov     rcx, rbx; hMem
0x180052e40  call    cs:__imp_LocalFree
0x180052e46  mov     rbx, [rsp+58h+arg_0]
0x180052e4b  mov     eax, esi
0x180052e4d  add     rsp, 20h
0x180052e51  pop     r15
0x180052e53  pop     r14
0x180052e55  pop     r13
0x180052e57  pop     r12
0x180052e59  pop     rdi
0x180052e5a  pop     rsi
0x180052e5b  pop     rbp
0x180052e5c  retn
```
