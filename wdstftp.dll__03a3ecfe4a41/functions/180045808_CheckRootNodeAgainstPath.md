# CheckRootNodeAgainstPath

- ea: `0x180045808`
- end: `0x180045920`
- name: `CheckRootNodeAgainstPath`
- size: `280`
- prototype: `__int64 __fastcall(Unattend *this, struct UnattendNode *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180045928`
- `0x180045abc`

## callees

- `0x180041a74`
- `0x180044e48`
- `0x180045074`
- `0x180045808`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800458e2`
- `KERNEL32!HeapFree` at `0x180045907`
- `KERNEL32!HeapFree` at `0x1800458e2`
- `KERNEL32!HeapFree` at `0x180045907`
- `KERNEL32!GetProcessHeap` at `0x1800458ce`
- `KERNEL32!GetProcessHeap` at `0x1800458f3`
- `KERNEL32!GetProcessHeap` at `0x1800458ce`
- `KERNEL32!GetProcessHeap` at `0x1800458f3`
- `KERNEL32!CompareStringW` at `0x1800458a7`
- `KERNEL32!CompareStringW` at `0x1800458a7`

## pseudocode

```c
__int64 __fastcall CheckRootNodeAgainstPath(Unattend *this, struct UnattendNode *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rsi
  int RootNode; // ebx
  WCHAR *v8; // rdi
  int PathElement; // eax
  WCHAR *v10; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v12; // rax
  PCNZWCH lpString2; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-40h] BYREF
  PCNZWCH lpString1; // [rsp+40h] [rbp-38h] BYREF

  v3 = *a3;
  v15 = *a3;
  RootNode = Unattend::GetRootNode(this, a2);
  if ( RootNode >= 0 )
  {
    RootNode = Unattend::GetName(this, a2, (unsigned __int16 **)&lpString1);
    if ( RootNode >= 0 )
    {
      lpString2 = 0;
      v8 = (WCHAR *)lpString1;
      if ( v3 )
      {
        PathElement = NextPathElement((const unsigned __int16 **)&v15, (unsigned __int16 **)&lpString2);
        RootNode = PathElement;
        if ( PathElement == 1 )
        {
          RootNode = -2147024883;
        }
        else if ( PathElement >= 0 )
        {
          v10 = (WCHAR *)lpString2;
          if ( CompareStringW(0x409u, 1u, v8, -1, lpString2, -1) == 2 )
          {
            RootNode = 0;
            *a3 = v15;
          }
          else
          {
            RootNode = -2147024883;
          }
          if ( v10 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v10);
          }
        }
      }
      else
      {
        RootNode = -2147024809;
      }
      if ( v8 )
      {
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v8);
      }
    }
  }
  return (unsigned int)RootNode;
}

```

## disassembly

```asm
0x180045808  push    rbx
0x18004580a  push    rbp
0x18004580b  push    rsi
0x18004580c  push    rdi
0x18004580d  push    r14
0x18004580f  sub     rsp, 50h
0x180045813  mov     rsi, [r8]
0x180045816  mov     r14, r8
0x180045819  mov     [rsp+78h+var_40], rsi
0x18004581e  mov     rbp, rdx
0x180045821  mov     rdi, rcx
0x180045824  call    ?GetRootNode@Unattend@@QEAAJAEAVUnattendNode@@@Z; Unattend::GetRootNode(UnattendNode &)
0x180045829  mov     ebx, eax
0x18004582b  test    eax, eax
0x18004582d  js      loc_180045913
0x180045833  lea     r8, [rsp+78h+lpString1]; unsigned __int16 **
0x180045838  mov     rdx, rbp; struct UnattendNode *
0x18004583b  mov     rcx, rdi; this
0x18004583e  call    ?GetName@Unattend@@QEAAJAEBVUnattendNode@@PEAPEAG@Z; Unattend::GetName(UnattendNode const &,ushort * *)
0x180045843  mov     ebx, eax
0x180045845  test    eax, eax
0x180045847  js      loc_180045913
0x18004584d  and     [rsp+78h+var_48], 0
0x180045853  mov     rdi, [rsp+78h+lpString1]
0x180045858  test    rsi, rsi
0x18004585b  jnz     short loc_180045867
0x18004585d  mov     ebx, 80070057h
0x180045862  jmp     loc_1800458EE
0x180045867  lea     rdx, [rsp+78h+var_48]; unsigned __int16 **
0x18004586c  lea     rcx, [rsp+78h+var_40]; unsigned __int16 **
0x180045871  call    ?NextPathElement@@YAJAEAPEBGAEAPEAG@Z; NextPathElement(ushort const * &,ushort * &)
0x180045876  mov     edx, 1; dwCmpFlags
0x18004587b  mov     ebx, eax
0x18004587d  cmp     eax, edx
0x18004587f  jnz     short loc_180045888
0x180045881  mov     ebx, 8007000Dh
0x180045886  jmp     short loc_1800458EE
0x180045888  test    eax, eax
0x18004588a  js      short loc_1800458EE
0x18004588c  mov     rsi, [rsp+78h+var_48]
0x180045891  or      r9d, 0FFFFFFFFh; cchCount1
0x180045895  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x18004589a  mov     r8, rdi; lpString1
0x18004589d  mov     ecx, 409h; Locale
0x1800458a2  mov     [rsp+78h+lpString2], rsi; lpString2
0x1800458a7  call    cs:__imp_CompareStringW
0x1800458ae  nop     dword ptr [rax+rax+00h]
0x1800458b3  cmp     eax, 2
0x1800458b6  jnz     short loc_1800458C4
0x1800458b8  mov     rax, [rsp+78h+var_40]
0x1800458bd  xor     ebx, ebx
0x1800458bf  mov     [r14], rax
0x1800458c2  jmp     short loc_1800458C9
0x1800458c4  mov     ebx, 8007000Dh
0x1800458c9  test    rsi, rsi
0x1800458cc  jz      short loc_1800458EE
0x1800458ce  call    cs:__imp_GetProcessHeap
0x1800458d5  nop     dword ptr [rax+rax+00h]
0x1800458da  mov     r8, rsi; lpMem
0x1800458dd  xor     edx, edx; dwFlags
0x1800458df  mov     rcx, rax; hHeap
0x1800458e2  call    cs:__imp_HeapFree
0x1800458e9  nop     dword ptr [rax+rax+00h]
0x1800458ee  test    rdi, rdi
0x1800458f1  jz      short loc_180045913
0x1800458f3  call    cs:__imp_GetProcessHeap
0x1800458fa  nop     dword ptr [rax+rax+00h]
0x1800458ff  mov     r8, rdi; lpMem
0x180045902  xor     edx, edx; dwFlags
0x180045904  mov     rcx, rax; hHeap
0x180045907  call    cs:__imp_HeapFree
0x18004590e  nop     dword ptr [rax+rax+00h]
0x180045913  mov     eax, ebx
0x180045915  add     rsp, 50h
0x180045919  pop     r14
0x18004591b  pop     rdi
0x18004591c  pop     rsi
0x18004591d  pop     rbp
0x18004591e  pop     rbx
0x18004591f  retn
```
