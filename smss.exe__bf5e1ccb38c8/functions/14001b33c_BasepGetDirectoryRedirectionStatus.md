# BasepGetDirectoryRedirectionStatus

- ea: `0x14001b33c`
- end: `0x14001b449`
- name: `BasepGetDirectoryRedirectionStatus`
- size: `269`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14001a3fc`

## callees

- `0x14001b33c`
- `0x14001b450`
- `0x14001b8a4`
- `0x14001b8f0`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001b3bf`
- `ntdll!RtlAllocateHeap` at `0x14001b3bf`
- `ntdll!RtlFreeHeap` at `0x14001b41a`
- `ntdll!RtlFreeHeap` at `0x14001b41a`

## pseudocode

```c
NTSTATUS __fastcall BasepGetDirectoryRedirectionStatus(NTSTRSAFE_PCWSTR pszSrc, void *a2)
{
  NTSTATUS result; // eax
  size_t v5; // rdi
  wchar_t *v6; // rsi
  NTSTRSAFE_PCWSTR v7; // r11
  wchar_t *Heap; // rax
  wchar_t *v9; // r11
  int FileRedirectionStatus; // ebx
  size_t pcchLength[2]; // [rsp+20h] [rbp-258h] BYREF
  char v12; // [rsp+30h] [rbp-248h] BYREF

  pcchLength[0] = 0;
  result = RtlStringCchLengthW(pszSrc, 0x7FFFFFFFu, pcchLength);
  if ( result >= 0 )
  {
    v5 = pcchLength[0];
    v6 = 0;
    if ( pszSrc[pcchLength[0] - 1] == 92 )
    {
      v7 = pszSrc;
    }
    else
    {
      if ( pcchLength[0] + 2 <= 0x104 )
      {
        v9 = (wchar_t *)&v12;
      }
      else
      {
        Heap = (wchar_t *)RtlAllocateHeap(
                            *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                            0,
                            2 * (pcchLength[0] + 2));
        v9 = Heap;
        if ( !Heap )
          return -1073741801;
        v6 = Heap;
      }
      FileRedirectionStatus = RtlStringCchCopyW(v9, v5 + 2, pszSrc);
      if ( FileRedirectionStatus < 0 )
      {
LABEL_12:
        if ( v6 )
          RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v6);
        return FileRedirectionStatus;
      }
      *(_DWORD *)&v7[v5] = 92;
    }
    FileRedirectionStatus = BasepGetFileRedirectionStatus((__int64)v7, a2);
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x14001b33c  mov     [rsp+arg_10], rbx
0x14001b341  push    rbp
0x14001b342  push    rsi
0x14001b343  push    rdi
0x14001b344  push    r14
0x14001b346  push    r15
0x14001b348  sub     rsp, 250h
0x14001b34f  mov     rax, cs:__security_cookie
0x14001b356  xor     rax, rsp
0x14001b359  mov     [rsp+278h+var_38], rax
0x14001b361  mov     rbp, rdx
0x14001b364  mov     [rsp+278h+pcchLength], 0
0x14001b36d  mov     edx, 7FFFFFFFh; cchMax
0x14001b372  lea     r8, [rsp+278h+pcchLength]; pcchLength
0x14001b377  mov     rbx, rcx
0x14001b37a  call    RtlStringCchLengthW
0x14001b37f  test    eax, eax
0x14001b381  js      loc_14001B422
0x14001b387  mov     rdi, [rsp+278h+pcchLength]
0x14001b38c  xor     esi, esi
0x14001b38e  lea     r15d, [rsi+5Ch]
0x14001b392  cmp     [rbx+rdi*2-2], r15w
0x14001b398  jnz     short loc_14001B39F
0x14001b39a  mov     r11, rbx
0x14001b39d  jmp     short loc_14001B3F6
0x14001b39f  lea     r14, [rdi+2]
0x14001b3a3  cmp     r14, 104h
0x14001b3aa  jbe     short loc_14001B3D9
0x14001b3ac  mov     rcx, gs:60h
0x14001b3b5  lea     r8, [r14+r14]; Size
0x14001b3b9  xor     edx, edx; Flags
0x14001b3bb  mov     rcx, [rcx+30h]; HeapHandle
0x14001b3bf  call    cs:__imp_RtlAllocateHeap
0x14001b3c5  mov     r11, rax
0x14001b3c8  test    rax, rax
0x14001b3cb  jnz     short loc_14001B3D4
0x14001b3cd  mov     ebx, 0C0000017h
0x14001b3d2  jmp     short loc_14001B420
0x14001b3d4  mov     rsi, rax
0x14001b3d7  jmp     short loc_14001B3DE
0x14001b3d9  lea     r11, [rsp+278h+var_248]
0x14001b3de  mov     r8, rbx; pszSrc
0x14001b3e1  mov     rdx, r14; cchDest
0x14001b3e4  mov     rcx, r11; pszDest
0x14001b3e7  call    RtlStringCchCopyW
0x14001b3ec  mov     ebx, eax
0x14001b3ee  test    eax, eax
0x14001b3f0  js      short loc_14001B403
0x14001b3f2  mov     [r11+rdi*2], r15d
0x14001b3f6  mov     rdx, rbp
0x14001b3f9  mov     rcx, r11
0x14001b3fc  call    BasepGetFileRedirectionStatus
0x14001b401  mov     ebx, eax
0x14001b403  test    rsi, rsi
0x14001b406  jz      short loc_14001B420
0x14001b408  mov     rcx, gs:60h
0x14001b411  mov     r8, rsi; BaseAddress
0x14001b414  xor     edx, edx; Flags
0x14001b416  mov     rcx, [rcx+30h]; HeapHandle
0x14001b41a  call    cs:__imp_RtlFreeHeap
0x14001b420  mov     eax, ebx
0x14001b422  mov     rcx, [rsp+278h+var_38]
0x14001b42a  xor     rcx, rsp; StackCookie
0x14001b42d  call    __security_check_cookie
0x14001b432  mov     rbx, [rsp+278h+arg_10]
0x14001b43a  add     rsp, 250h
0x14001b441  pop     r15
0x14001b443  pop     r14
0x14001b445  pop     rdi
0x14001b446  pop     rsi
0x14001b447  pop     rbp
0x14001b448  retn
```
