# WDSGetImageXml(IDepImageInfo *,_WDS_IMAGE_INFO *)

- ea: `0x180002edc`
- end: `0x180003008`
- name: `?WDSGetImageXml@@YAJPEAVIDepImageInfo@@PEAU_WDS_IMAGE_INFO@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(struct IDepImageInfo *, struct _WDS_IMAGE_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000284c`

## callees

- `0x1800024b4`
- `0x180002edc`
- `0x180003208`
- `0x180011010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180002f6b`
- `KERNEL32!HeapAlloc` at `0x180002f6b`
- `KERNEL32!GetProcessHeap` at `0x180002f56`
- `KERNEL32!GetProcessHeap` at `0x180002fd8`
- `KERNEL32!GetProcessHeap` at `0x180002f56`
- `KERNEL32!GetProcessHeap` at `0x180002fd8`
- `KERNEL32!HeapFree` at `0x180002fec`
- `KERNEL32!HeapFree` at `0x180002fec`

## pseudocode

```c
__int64 __fastcall WDSGetImageXml(struct IDepImageInfo *a1, struct _WDS_IMAGE_INFO *a2)
{
  __int64 v2; // rax
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  size_t v7; // rcx
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  void *Src; // [rsp+40h] [rbp+8h] BYREF
  size_t Size; // [rsp+50h] [rbp+18h] BYREF

  v2 = *(_QWORD *)a1;
  Src = 0;
  Size = 0;
  v4 = (*(__int64 (__fastcall **)(struct IDepImageInfo *, void **, size_t *))(v2 + 48))(a1, &Src, &Size);
  if ( (int)ElValidateHr(v4, v5, v6, 350) >= 0 )
  {
    v7 = Size;
    if ( (Size & 1) != 0 || !Size )
    {
      v4 = -2147024883;
    }
    else if ( *((_WORD *)Src + (Size >> 1) - 1) )
    {
      v8 = Size + 2;
      *((_QWORD *)a2 + 22) = Size + 2;
      ProcessHeap = GetProcessHeap();
      v10 = HeapAlloc(ProcessHeap, 8u, v8);
      *((_QWORD *)a2 + 21) = v10;
      if ( v10 )
      {
        memmove_0(v10, Src, Size);
        *(_WORD *)(*((_QWORD *)a2 + 21) + 2LL * (*((_QWORD *)a2 + 22) >> 1) - 2) = 0;
      }
      else
      {
        v4 = -2147024882;
      }
    }
    else
    {
      *((_QWORD *)a2 + 21) = Src;
      *((_QWORD *)a2 + 22) = v7;
      Src = 0;
    }
  }
  v11 = Src;
  if ( Src )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  return v4;
}

```

## disassembly

```asm
0x180002edc  mov     r11, rsp
0x180002edf  mov     [r11+10h], rbx
0x180002ee3  push    rbp
0x180002ee4  push    rsi
0x180002ee5  push    rdi
0x180002ee6  sub     rsp, 20h
0x180002eea  mov     rax, [rcx]
0x180002eed  lea     r8, [r11+18h]
0x180002ef1  mov     rdi, rdx
0x180002ef4  xor     ebp, ebp
0x180002ef6  lea     rdx, [r11+8]
0x180002efa  mov     [r11+8], rbp
0x180002efe  mov     [r11+18h], rbp
0x180002f02  mov     rax, [rax+30h]
0x180002f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f0b  mov     r9d, 15Eh
0x180002f11  mov     ecx, eax
0x180002f13  mov     esi, eax
0x180002f15  call    ElValidateHr
0x180002f1a  test    eax, eax
0x180002f1c  js      loc_180002FCE
0x180002f22  mov     rcx, [rsp+38h+Size]
0x180002f27  test    cl, 1
0x180002f2a  jnz     loc_180002FC9
0x180002f30  test    rcx, rcx
0x180002f33  jz      loc_180002FC9
0x180002f39  mov     rdx, [rsp+38h+Src]
0x180002f3e  mov     rax, rcx
0x180002f41  shr     rax, 1
0x180002f44  cmp     [rdx+rax*2-2], bp
0x180002f49  jz      short loc_180002FB4
0x180002f4b  lea     rbx, [rcx+2]
0x180002f4f  mov     [rdi+0B0h], rbx
0x180002f56  call    cs:__imp_GetProcessHeap
0x180002f5d  nop     dword ptr [rax+rax+00h]
0x180002f62  mov     r8, rbx; dwBytes
0x180002f65  lea     edx, [rbp+8]; dwFlags
0x180002f68  mov     rcx, rax; hHeap
0x180002f6b  call    cs:__imp_HeapAlloc
0x180002f72  nop     dword ptr [rax+rax+00h]
0x180002f77  mov     [rdi+0A8h], rax
0x180002f7e  test    rax, rax
0x180002f81  jnz     short loc_180002F8A
0x180002f83  mov     esi, 8007000Eh
0x180002f88  jmp     short loc_180002FCE
0x180002f8a  mov     r8, [rsp+38h+Size]; Size
0x180002f8f  mov     rcx, rax; void *
0x180002f92  mov     rdx, [rsp+38h+Src]; Src
0x180002f97  call    memmove_0
0x180002f9c  mov     rcx, [rdi+0B0h]
0x180002fa3  mov     rax, [rdi+0A8h]
0x180002faa  shr     rcx, 1
0x180002fad  mov     [rax+rcx*2-2], bp
0x180002fb2  jmp     short loc_180002FCE
0x180002fb4  mov     [rdi+0A8h], rdx
0x180002fbb  mov     [rdi+0B0h], rcx
0x180002fc2  mov     [rsp+38h+Src], rbp
0x180002fc7  jmp     short loc_180002FCE
0x180002fc9  mov     esi, 8007000Dh
0x180002fce  mov     rbx, [rsp+38h+Src]
0x180002fd3  test    rbx, rbx
0x180002fd6  jz      short loc_180002FF8
0x180002fd8  call    cs:__imp_GetProcessHeap
0x180002fdf  nop     dword ptr [rax+rax+00h]
0x180002fe4  mov     r8, rbx; lpMem
0x180002fe7  xor     edx, edx; dwFlags
0x180002fe9  mov     rcx, rax; hHeap
0x180002fec  call    cs:__imp_HeapFree
0x180002ff3  nop     dword ptr [rax+rax+00h]
0x180002ff8  mov     rbx, [rsp+38h+arg_8]
0x180002ffd  mov     eax, esi
0x180002fff  add     rsp, 20h
0x180003003  pop     rdi
0x180003004  pop     rsi
0x180003005  pop     rbp
0x180003006  retn
```
