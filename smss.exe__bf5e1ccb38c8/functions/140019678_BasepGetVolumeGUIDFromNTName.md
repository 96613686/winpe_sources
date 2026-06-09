# BasepGetVolumeGUIDFromNTName

- ea: `0x140019678`
- end: `0x140019976`
- name: `BasepGetVolumeGUIDFromNTName`
- size: `766`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140019a5c`

## callees

- `0x140019678`
- `0x14001997c`
- `0x14001abac`
- `0x14001ac48`
- `0x14001cc11`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400196fb`
- `ntdll!RtlAllocateHeap` at `0x14001977a`
- `ntdll!RtlAllocateHeap` at `0x1400198ba`
- `ntdll!RtlAllocateHeap` at `0x1400196fb`
- `ntdll!RtlAllocateHeap` at `0x14001977a`
- `ntdll!RtlAllocateHeap` at `0x1400198ba`
- `ntdll!RtlFreeHeap` at `0x14001975e`
- `ntdll!RtlFreeHeap` at `0x1400198fd`
- `ntdll!RtlFreeHeap` at `0x140019940`
- `ntdll!RtlFreeHeap` at `0x14001995d`
- `ntdll!RtlFreeHeap` at `0x14001975e`
- `ntdll!RtlFreeHeap` at `0x1400198fd`
- `ntdll!RtlFreeHeap` at `0x140019940`
- `ntdll!RtlFreeHeap` at `0x14001995d`
- `ntdll!wcslen` at `0x1400196d7`
- `ntdll!wcslen` at `0x140019724`
- `ntdll!wcslen` at `0x1400196d7`
- `ntdll!wcslen` at `0x140019724`
- `ntdll!RtlSetLastWin32Error` at `0x14001990c`
- `ntdll!RtlSetLastWin32Error` at `0x140019919`
- `ntdll!RtlSetLastWin32Error` at `0x14001990c`
- `ntdll!RtlSetLastWin32Error` at `0x140019919`

## string_xrefs

- `0x1400196b3`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall BasepGetVolumeGUIDFromNTName(const wchar_t *Src, _QWORD *a2)
{
  void *FileW; // r12
  unsigned int v5; // esi
  _DWORD *v6; // rdi
  int v7; // eax
  _QWORD *Heap; // rbp
  unsigned __int16 v9; // ax
  ULONG i; // ebx
  int v11; // r8d
  __int64 v12; // rax
  int j; // edx
  __int64 v14; // r9
  _WORD *v15; // rbx
  size_t v16; // r15
  _WORD *v17; // rax
  _WORD *v18; // r14
  __int64 v20; // [rsp+A0h] [rbp+18h] BYREF

  LODWORD(v20) = 0;
  FileW = (void *)CreateFileW();
  if ( FileW == (void *)-1LL )
  {
    return 0;
  }
  else
  {
    v6 = 0;
    v7 = wcslen(Src);
    Heap = RtlAllocateHeap(
             *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
             KernelBaseGlobalData,
             (unsigned int)(2 * v7 + 24));
    if ( Heap )
    {
      *(_OWORD *)Heap = 0;
      Heap[2] = 0;
      *((_DWORD *)Heap + 4) = 24;
      v9 = 2 * wcslen(Src);
      *((_WORD *)Heap + 10) = v9;
      memcpy_0(Heap + 3, Src, v9);
      for ( i = 672; ; i = *v6 + 32 )
      {
        if ( v6 )
          RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v6);
        v6 = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), KernelBaseGlobalData, i);
        if ( !v6 )
          break;
        v5 = DeviceIoControl(FileW, 0x6D0008u, (__int64)v6, i, (__int64)&v20);
        if ( v5 )
        {
          v11 = 0;
          v12 = 0;
          for ( j = 0; ; j = v11 )
          {
            if ( (unsigned int)v12 >= v6[1] )
            {
              RtlSetLastWin32Error(0x32u);
              goto LABEL_39;
            }
            v14 = LOWORD(v6[6 * v12 + 3]);
            v15 = (_WORD *)((char *)v6 + (unsigned int)v6[6 * j + 2]);
            if ( ((_DWORD)v14 == 96 || (_DWORD)v14 == 98 && v15[48] == 92)
              && *v15 == 92
              && (v15[1] == 63 || v15[1] == 92)
              && v15[2] == 63
              && v15[3] == 92
              && v15[4] == 86
              && v15[5] == 111
              && v15[6] == 108
              && v15[7] == 117
              && v15[8] == 109
              && v15[9] == 101
              && v15[10] == 123
              && v15[19] == 45
              && v15[24] == 45
              && v15[29] == 45
              && v15[34] == 45
              && v15[47] == 125 )
            {
              break;
            }
            v12 = (unsigned int)++v11;
          }
          v16 = LOWORD(v6[6 * v12 + 3]);
          v17 = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), KernelBaseGlobalData, v14 + 2);
          *a2 = v17;
          v18 = v17;
          if ( !v17 )
            break;
          memcpy_0(v17, v15, v16);
          v18[v16 >> 1] = 0;
          v18[1] = 92;
LABEL_36:
          RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v6);
          v6 = 0;
          goto LABEL_39;
        }
        if ( LODWORD(KeGetPcr()->Unused1[0]) != 234 )
          goto LABEL_36;
      }
    }
    RtlSetLastWin32Error(8u);
    v5 = 0;
LABEL_39:
    CloseHandle(FileW);
    if ( Heap )
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
    if ( v6 )
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v6);
  }
  return v5;
}

```

## disassembly

```asm
0x140019678  mov     rax, rsp
0x14001967b  push    rbx
0x14001967c  push    rbp
0x14001967d  push    rsi
0x14001967e  push    rdi
0x14001967f  push    r12
0x140019681  push    r13
0x140019683  push    r14
0x140019685  push    r15
0x140019687  sub     rsp, 48h
0x14001968b  mov     qword ptr [rax-58h], 0
0x140019693  mov     r13, rdx
0x140019696  mov     rbx, rcx
0x140019699  mov     dword ptr [rax-60h], 80h
0x1400196a0  mov     r8d, 3
0x1400196a6  mov     dword ptr [rax+18h], 0
0x1400196ad  xor     edx, edx
0x1400196af  mov     [rax-68h], r8d
0x1400196b3  lea     rcx, aMountpointmana; "\\\\.\\MountPointManager"
0x1400196ba  xor     r9d, r9d
0x1400196bd  call    CreateFileW
0x1400196c2  mov     r12, rax
0x1400196c5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400196c9  jnz     short loc_1400196D2
0x1400196cb  xor     esi, esi
0x1400196cd  jmp     loc_140019963
0x1400196d2  mov     rcx, rbx; Str
0x1400196d5  xor     edi, edi
0x1400196d7  call    cs:__imp_wcslen
0x1400196dd  mov     rcx, gs:60h
0x1400196e6  mov     edx, cs:KernelBaseGlobalData; Flags
0x1400196ec  lea     r14d, ds:18h[rax*2]
0x1400196f4  mov     rcx, [rcx+30h]; HeapHandle
0x1400196f8  mov     r8d, r14d; Size
0x1400196fb  call    cs:__imp_RtlAllocateHeap
0x140019701  mov     rbp, rax
0x140019704  test    rax, rax
0x140019707  jz      loc_140019914
0x14001970d  xorps   xmm0, xmm0
0x140019710  xor     eax, eax
0x140019712  movups  xmmword ptr [rbp+0], xmm0
0x140019716  mov     [rbp+10h], rax
0x14001971a  mov     rcx, rbx; Str
0x14001971d  mov     dword ptr [rbp+10h], 18h
0x140019724  call    cs:__imp_wcslen
0x14001972a  lea     rcx, [rbp+18h]; void *
0x14001972e  mov     rdx, rbx; Src
0x140019731  add     ax, ax
0x140019734  movzx   r8d, ax; MaxCount
0x140019738  mov     [rbp+14h], r8w
0x14001973d  call    memcpy_0
0x140019742  mov     ebx, 2A0h
0x140019747  test    rdi, rdi
0x14001974a  jz      short loc_140019764
0x14001974c  mov     rcx, gs:60h
0x140019755  mov     r8, rdi; BaseAddress
0x140019758  xor     edx, edx; Flags
0x14001975a  mov     rcx, [rcx+30h]; HeapHandle
0x14001975e  call    cs:__imp_RtlFreeHeap
0x140019764  mov     rcx, gs:60h
0x14001976d  mov     edx, cs:KernelBaseGlobalData; Flags
0x140019773  mov     r8d, ebx; Size
0x140019776  mov     rcx, [rcx+30h]; HeapHandle
0x14001977a  call    cs:__imp_RtlAllocateHeap
0x140019780  mov     rdi, rax
0x140019783  test    rax, rax
0x140019786  jz      loc_140019914
0x14001978c  lea     rax, [rsp+88h+arg_10]
0x140019794  mov     r9d, r14d
0x140019797  mov     [rsp+88h+var_58], rax; __int64
0x14001979c  mov     r8, rbp
0x14001979f  mov     [rsp+88h+var_60], ebx; ULONG
0x1400197a3  mov     edx, 6D0008h; FsControlCode
0x1400197a8  mov     rcx, r12; Object
0x1400197ab  mov     [rsp+88h+var_68], rdi; __int64
0x1400197b0  call    DeviceIoControl
0x1400197b5  mov     esi, eax
0x1400197b7  test    eax, eax
0x1400197b9  jnz     short loc_1400197D9
0x1400197bb  mov     ecx, gs:68h
0x1400197c3  cmp     ecx, 0EAh
0x1400197c9  jnz     loc_1400198EB
0x1400197cf  mov     ebx, [rdi]
0x1400197d1  add     ebx, 20h ; ' '
0x1400197d4  jmp     loc_140019747
0x1400197d9  xor     r8d, r8d
0x1400197dc  xor     eax, eax
0x1400197de  xor     edx, edx
0x1400197e0  mov     r11w, 2Dh ; '-'
0x1400197e5  lea     r10d, [r8+5Ch]
0x1400197e9  cmp     eax, [rdi+4]
0x1400197ec  jnb     loc_140019907
0x1400197f2  lea     rcx, [rax+rax*2]
0x1400197f6  mov     eax, edx
0x1400197f8  movzx   r9d, word ptr [rdi+rcx*8+0Ch]
0x1400197fe  lea     rcx, [rax+rax*2]
0x140019802  mov     ebx, [rdi+rcx*8+8]
0x140019806  add     rbx, rdi
0x140019809  cmp     r9d, 60h ; '`'
0x14001980d  jz      short loc_14001981C
0x14001980f  cmp     r9d, 62h ; 'b'
0x140019813  jnz     short loc_140019892
0x140019815  cmp     [rbx+60h], r10w
0x14001981a  jnz     short loc_140019892
0x14001981c  cmp     [rbx], r10w
0x140019820  jnz     short loc_140019892
0x140019822  cmp     word ptr [rbx+2], 3Fh ; '?'
0x140019827  jz      short loc_140019830
0x140019829  cmp     [rbx+2], r10w
0x14001982e  jnz     short loc_140019892
0x140019830  cmp     word ptr [rbx+4], 3Fh ; '?'
0x140019835  jnz     short loc_140019892
0x140019837  cmp     [rbx+6], r10w
0x14001983c  jnz     short loc_140019892
0x14001983e  cmp     word ptr [rbx+8], 56h ; 'V'
0x140019843  jnz     short loc_140019892
0x140019845  cmp     word ptr [rbx+0Ah], 6Fh ; 'o'
0x14001984a  jnz     short loc_140019892
0x14001984c  cmp     word ptr [rbx+0Ch], 6Ch ; 'l'
0x140019851  jnz     short loc_140019892
0x140019853  cmp     word ptr [rbx+0Eh], 75h ; 'u'
0x140019858  jnz     short loc_140019892
0x14001985a  cmp     word ptr [rbx+10h], 6Dh ; 'm'
0x14001985f  jnz     short loc_140019892
0x140019861  cmp     word ptr [rbx+12h], 65h ; 'e'
0x140019866  jnz     short loc_140019892
0x140019868  cmp     word ptr [rbx+14h], 7Bh ; '{'
0x14001986d  jnz     short loc_140019892
0x14001986f  cmp     [rbx+26h], r11w
0x140019874  jnz     short loc_140019892
0x140019876  cmp     [rbx+30h], r11w
0x14001987b  jnz     short loc_140019892
0x14001987d  cmp     [rbx+3Ah], r11w
0x140019882  jnz     short loc_140019892
0x140019884  cmp     [rbx+44h], r11w
0x140019889  jnz     short loc_140019892
0x14001988b  cmp     word ptr [rbx+5Eh], 7Dh ; '}'
0x140019890  jz      short loc_1400198A0
0x140019892  inc     r8d
0x140019895  mov     eax, r8d
0x140019898  mov     edx, r8d
0x14001989b  jmp     loc_1400197E9
0x1400198a0  mov     rcx, gs:60h
0x1400198a9  lea     r8, [r9+2]; Size
0x1400198ad  mov     edx, cs:KernelBaseGlobalData; Flags
0x1400198b3  mov     r15, r9
0x1400198b6  mov     rcx, [rcx+30h]; HeapHandle
0x1400198ba  call    cs:__imp_RtlAllocateHeap
0x1400198c0  mov     [r13+0], rax
0x1400198c4  mov     r14, rax
0x1400198c7  test    rax, rax
0x1400198ca  jz      short loc_140019914
0x1400198cc  mov     r8, r15; MaxCount
0x1400198cf  mov     rdx, rbx; Src
0x1400198d2  mov     rcx, rax; void *
0x1400198d5  call    memcpy_0
0x1400198da  shr     r15, 1
0x1400198dd  xor     eax, eax
0x1400198df  mov     [r14+r15*2], ax
0x1400198e4  mov     word ptr [r14+2], 5Ch ; '\'
0x1400198eb  mov     rcx, gs:60h
0x1400198f4  mov     r8, rdi; BaseAddress
0x1400198f7  xor     edx, edx; Flags
0x1400198f9  mov     rcx, [rcx+30h]; HeapHandle
0x1400198fd  call    cs:__imp_RtlFreeHeap
0x140019903  xor     edi, edi
0x140019905  jmp     short loc_140019921
0x140019907  mov     ecx, 32h ; '2'; LastError
0x14001990c  call    cs:__imp_RtlSetLastWin32Error
0x140019912  jmp     short loc_140019921
0x140019914  mov     ecx, 8; LastError
0x140019919  call    cs:__imp_RtlSetLastWin32Error
0x14001991f  xor     esi, esi
0x140019921  mov     rcx, r12; Handle
0x140019924  call    CloseHandle
0x140019929  test    rbp, rbp
0x14001992c  jz      short loc_140019946
0x14001992e  mov     rcx, gs:60h
0x140019937  mov     r8, rbp; BaseAddress
0x14001993a  xor     edx, edx; Flags
0x14001993c  mov     rcx, [rcx+30h]; HeapHandle
0x140019940  call    cs:__imp_RtlFreeHeap
0x140019946  test    rdi, rdi
0x140019949  jz      short loc_140019963
0x14001994b  mov     rcx, gs:60h
0x140019954  mov     r8, rdi; BaseAddress
0x140019957  xor     edx, edx; Flags
0x140019959  mov     rcx, [rcx+30h]; HeapHandle
0x14001995d  call    cs:__imp_RtlFreeHeap
0x140019963  mov     eax, esi
0x140019965  add     rsp, 48h
0x140019969  pop     r15
0x14001996b  pop     r14
0x14001996d  pop     r13
0x14001996f  pop     r12
0x140019971  pop     rdi
0x140019972  pop     rsi
0x140019973  pop     rbp
0x140019974  pop     rbx
0x140019975  retn
```
