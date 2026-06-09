# CanonicalizeObjectPathByHandle

- ea: `0x180014fa0`
- end: `0x180015129`
- name: `CanonicalizeObjectPathByHandle`
- size: `393`
- prototype: `__int64 __fastcall(HANDLE Handle, _QWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x180008d44`
- `0x18000acec`
- `0x18000dae0`
- `0x180010b08`
- `0x1800111bc`
- `0x180014ebc`

## callees

- `0x180001464`
- `0x180014fa0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180014fe2`
- `ntdll!RtlAllocateHeap` at `0x180015057`
- `ntdll!RtlAllocateHeap` at `0x1800150a3`
- `ntdll!RtlAllocateHeap` at `0x180014fe2`
- `ntdll!RtlAllocateHeap` at `0x180015057`
- `ntdll!RtlAllocateHeap` at `0x1800150a3`
- `ntdll!RtlFreeHeap` at `0x180015038`
- `ntdll!RtlFreeHeap` at `0x1800150f3`
- `ntdll!RtlFreeHeap` at `0x180015110`
- `ntdll!RtlFreeHeap` at `0x180015038`
- `ntdll!RtlFreeHeap` at `0x1800150f3`
- `ntdll!RtlFreeHeap` at `0x180015110`
- `ntdll!NtQueryObject` at `0x180015012`
- `ntdll!NtQueryObject` at `0x18001507d`
- `ntdll!NtQueryObject` at `0x180015012`
- `ntdll!NtQueryObject` at `0x18001507d`

## pseudocode

```c
__int64 __fastcall CanonicalizeObjectPathByHandle(HANDLE Handle, _QWORD *a2)
{
  _QWORD *Heap; // rdi
  NTSTATUS v5; // ebx
  ULONG v6; // esi
  PVOID v7; // rax
  void *v8; // rsi
  ULONG ObjectInformationLength; // [rsp+60h] [rbp+8h] BYREF

  ObjectInformationLength = 0;
  if ( Handle && a2 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
    if ( !Heap )
      return (unsigned int)-1073741801;
    if ( NtQueryObject(Handle, ObjectNameInformation, Heap, 0x10u, &ObjectInformationLength) >= 0 )
      goto LABEL_9;
    if ( ObjectInformationLength < 0x10 )
    {
      v5 = -1073741820;
    }
    else
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v6 = ObjectInformationLength;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ObjectInformationLength);
      if ( !Heap )
        return (unsigned int)-1073741801;
      v5 = NtQueryObject(Handle, ObjectNameInformation, Heap, v6, &ObjectInformationLength);
      if ( v5 >= 0 )
      {
LABEL_9:
        v7 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, *(unsigned __int16 *)Heap + 2LL);
        v8 = v7;
        if ( v7 )
        {
          v5 = RtlStringCchCopyNW(v7, ((unsigned __int64)*(unsigned __int16 *)Heap >> 1) + 1, Heap[1]);
          if ( v5 < 0 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
          else
            *a2 = v8;
        }
        else
        {
          v5 = -1073741801;
        }
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    return (unsigned int)v5;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180014fa0  push    rbx
0x180014fa2  push    rsi
0x180014fa3  push    rdi
0x180014fa4  push    r14
0x180014fa6  sub     rsp, 38h
0x180014faa  mov     [rsp+58h+ObjectInformationLength], 0
0x180014fb2  mov     r14, rdx
0x180014fb5  mov     rbx, rcx
0x180014fb8  test    rcx, rcx
0x180014fbb  jz      loc_18001511A
0x180014fc1  test    rdx, rdx
0x180014fc4  jz      loc_18001511A
0x180014fca  mov     rcx, gs:60h
0x180014fd3  mov     esi, 10h
0x180014fd8  mov     r8d, esi; Size
0x180014fdb  mov     rcx, [rcx+30h]; HeapHandle
0x180014fdf  lea     edx, [rsi-8]; Flags
0x180014fe2  call    cs:__imp_RtlAllocateHeap
0x180014fe8  mov     rdi, rax
0x180014feb  test    rax, rax
0x180014fee  jnz     short loc_180014FFA
0x180014ff0  mov     ebx, 0C0000017h
0x180014ff5  jmp     loc_180015116
0x180014ffa  lea     rax, [rsp+58h+ObjectInformationLength]
0x180014fff  mov     r9d, esi; ObjectInformationLength
0x180015002  mov     r8, rdi; ObjectInformation
0x180015005  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001500a  mov     edx, 1; ObjectInformationClass
0x18001500f  mov     rcx, rbx; Handle
0x180015012  call    cs:__imp_NtQueryObject
0x180015018  test    eax, eax
0x18001501a  jns     short loc_180015089
0x18001501c  cmp     [rsp+58h+ObjectInformationLength], esi
0x180015020  jb      loc_1800150B8
0x180015026  mov     rcx, gs:60h
0x18001502f  mov     r8, rdi; P
0x180015032  xor     edx, edx; Flags
0x180015034  mov     rcx, [rcx+30h]; HeapHandle
0x180015038  call    cs:__imp_RtlFreeHeap
0x18001503e  mov     rcx, gs:60h
0x180015047  mov     edx, 8; Flags
0x18001504c  mov     esi, [rsp+58h+ObjectInformationLength]
0x180015050  mov     r8d, esi; Size
0x180015053  mov     rcx, [rcx+30h]; HeapHandle
0x180015057  call    cs:__imp_RtlAllocateHeap
0x18001505d  mov     rdi, rax
0x180015060  test    rax, rax
0x180015063  jz      short loc_180014FF0
0x180015065  lea     rax, [rsp+58h+ObjectInformationLength]
0x18001506a  mov     r9d, esi; ObjectInformationLength
0x18001506d  mov     r8, rdi; ObjectInformation
0x180015070  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180015075  mov     edx, 1; ObjectInformationClass
0x18001507a  mov     rcx, rbx; Handle
0x18001507d  call    cs:__imp_NtQueryObject
0x180015083  mov     ebx, eax
0x180015085  test    eax, eax
0x180015087  js      short loc_1800150FE
0x180015089  mov     rcx, gs:60h
0x180015092  mov     edx, 8; Flags
0x180015097  movzx   r8d, word ptr [rdi]
0x18001509b  add     r8, 2; Size
0x18001509f  mov     rcx, [rcx+30h]; HeapHandle
0x1800150a3  call    cs:__imp_RtlAllocateHeap
0x1800150a9  mov     rsi, rax
0x1800150ac  test    rax, rax
0x1800150af  jnz     short loc_1800150BF
0x1800150b1  mov     ebx, 0C0000017h
0x1800150b6  jmp     short loc_1800150F9
0x1800150b8  mov     ebx, 0C0000004h
0x1800150bd  jmp     short loc_1800150FE
0x1800150bf  movzx   r9d, word ptr [rdi]
0x1800150c3  mov     rcx, rsi
0x1800150c6  mov     r8, [rdi+8]
0x1800150ca  shr     r9, 1
0x1800150cd  lea     rdx, [r9+1]
0x1800150d1  call    RtlStringCchCopyNW
0x1800150d6  mov     ebx, eax
0x1800150d8  test    eax, eax
0x1800150da  js      short loc_1800150E1
0x1800150dc  mov     [r14], rsi
0x1800150df  jmp     short loc_1800150F9
0x1800150e1  mov     rcx, gs:60h
0x1800150ea  mov     r8, rsi; P
0x1800150ed  xor     edx, edx; Flags
0x1800150ef  mov     rcx, [rcx+30h]; HeapHandle
0x1800150f3  call    cs:__imp_RtlFreeHeap
0x1800150f9  test    rdi, rdi
0x1800150fc  jz      short loc_180015116
0x1800150fe  mov     rcx, gs:60h
0x180015107  mov     r8, rdi; P
0x18001510a  xor     edx, edx; Flags
0x18001510c  mov     rcx, [rcx+30h]; HeapHandle
0x180015110  call    cs:__imp_RtlFreeHeap
0x180015116  mov     eax, ebx
0x180015118  jmp     short loc_18001511F
0x18001511a  mov     eax, 0C000000Dh
0x18001511f  add     rsp, 38h
0x180015123  pop     r14
0x180015125  pop     rdi
0x180015126  pop     rsi
0x180015127  pop     rbx
0x180015128  retn
```
