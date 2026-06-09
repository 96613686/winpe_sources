# BasepGetVolumeDosLetterNameFromNTName

- ea: `0x14001933c`
- end: `0x14001966f`
- name: `BasepGetVolumeDosLetterNameFromNTName`
- size: `819`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140019a5c`

## callees

- `0x14001933c`
- `0x14001997c`
- `0x14001abac`
- `0x14001ac48`
- `0x14001cc11`
- `0x14001cc1d`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140019536`
- `ntdll!RtlInitUnicodeString` at `0x140019536`
- `ntdll!RtlAllocateHeap` at `0x140019390`
- `ntdll!RtlAllocateHeap` at `0x140019441`
- `ntdll!RtlAllocateHeap` at `0x1400194ab`
- `ntdll!RtlAllocateHeap` at `0x140019390`
- `ntdll!RtlAllocateHeap` at `0x140019441`
- `ntdll!RtlAllocateHeap` at `0x1400194ab`
- `ntdll!RtlFreeHeap` at `0x14001948f`
- `ntdll!RtlFreeHeap` at `0x140019520`
- `ntdll!RtlFreeHeap` at `0x140019639`
- `ntdll!RtlFreeHeap` at `0x140019656`
- `ntdll!RtlFreeHeap` at `0x14001948f`
- `ntdll!RtlFreeHeap` at `0x140019520`
- `ntdll!RtlFreeHeap` at `0x140019639`
- `ntdll!RtlFreeHeap` at `0x140019656`
- `ntdll!wcslen` at `0x14001941e`
- `ntdll!wcslen` at `0x140019456`
- `ntdll!wcslen` at `0x14001941e`
- `ntdll!wcslen` at `0x140019456`
- `ntdll!RtlSetLastWin32Error` at `0x1400193a5`
- `ntdll!RtlSetLastWin32Error` at `0x140019612`
- `ntdll!RtlSetLastWin32Error` at `0x1400193a5`
- `ntdll!RtlSetLastWin32Error` at `0x140019612`
- `ntdll!_wcsnicmp` at `0x140019368`
- `ntdll!_wcsnicmp` at `0x140019368`

## string_xrefs

- `0x140019404`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall BasepGetVolumeDosLetterNameFromNTName(const wchar_t *Src, _QWORD *a2)
{
  _DWORD *v4; // rax
  unsigned int v5; // esi
  void *FileW; // r12
  _QWORD *v8; // rdi
  int v9; // eax
  _WORD *Heap; // r14
  unsigned __int16 v11; // ax
  unsigned int i; // ebx
  _QWORD *v13; // rax
  WCHAR *v14; // r15
  ULONG v15; // ecx
  unsigned int v16; // eax
  unsigned __int64 v17; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF
  __int64 v19; // [rsp+B0h] [rbp+18h] BYREF

  DestinationString = 0;
  LODWORD(v19) = _wcsnicmp(Src, L"\\Device\\MUP", 0xBu);
  if ( (_DWORD)v19 )
  {
    FileW = (void *)CreateFileW();
    if ( FileW != (void *)-1LL )
    {
      v8 = 0;
      v9 = wcslen(Src);
      Heap = RtlAllocateHeap(
               *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
               KernelBaseGlobalData,
               (unsigned int)(2 * v9 + 4));
      if ( Heap )
      {
        v11 = 2 * wcslen(Src);
        *Heap = v11;
        memcpy_0(Heap + 1, Src, v11);
        for ( i = 536; ; i = *(_DWORD *)v14 + 16 )
        {
          if ( v8 )
            RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v8);
          v13 = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), KernelBaseGlobalData, i);
          v8 = v13;
          if ( !v13 )
            goto LABEL_39;
          v14 = (WCHAR *)(v13 + 1);
          v5 = DeviceIoControl(FileW, 0x6D0030u, (__int64)(v13 + 1), i - 8, (__int64)&v19);
          if ( v5 )
            break;
          if ( LODWORD(KeGetPcr()->Unused1[0]) != 234 )
          {
            RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v8);
LABEL_16:
            v8 = 0;
            goto LABEL_41;
          }
        }
        RtlInitUnicodeString(&DestinationString, v14 + 2);
        if ( DestinationString.Length != 96 && (DestinationString.Length != 98 || DestinationString.Buffer[48] != 92)
          || *DestinationString.Buffer != 92
          || DestinationString.Buffer[1] != 63 && DestinationString.Buffer[1] != 92
          || DestinationString.Buffer[2] != 63
          || DestinationString.Buffer[3] != 92
          || DestinationString.Buffer[4] != 86
          || DestinationString.Buffer[5] != 111
          || DestinationString.Buffer[6] != 108
          || DestinationString.Buffer[7] != 117
          || DestinationString.Buffer[8] != 109
          || DestinationString.Buffer[9] != 101
          || DestinationString.Buffer[10] != 123
          || DestinationString.Buffer[19] != 45
          || DestinationString.Buffer[24] != 45
          || DestinationString.Buffer[29] != 45
          || DestinationString.Buffer[34] != 45
          || DestinationString.Buffer[47] != 125 )
        {
          v16 = *(_DWORD *)v14;
          *a2 = v8;
          *v8 = 0x5C003F005C005CLL;
          v17 = v16;
          memmove_0(v14, v14 + 2, v16);
          *((_WORD *)v8 + (v17 >> 1) + 4) = 0;
          goto LABEL_16;
        }
        v15 = 3;
      }
      else
      {
LABEL_39:
        v15 = 8;
      }
      RtlSetLastWin32Error(v15);
      v5 = 0;
LABEL_41:
      CloseHandle(FileW);
      if ( v8 )
        RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v8);
      if ( Heap )
        RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
      return v5;
    }
  }
  else
  {
    v4 = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), KernelBaseGlobalData, 0x10u);
    *a2 = v4;
    if ( v4 )
    {
      *(_QWORD *)v4 = *(_QWORD *)L"\\\\?\\UNC";
      v4[2] = *(_DWORD *)L"UNC";
      *((_WORD *)v4 + 6) = aUnc_0[6];
      *((_WORD *)v4 + 7) = 0;
      return 1;
    }
    RtlSetLastWin32Error(8u);
  }
  return 0;
}

```

## disassembly

```asm
0x14001933c  push    rbx
0x14001933e  push    rbp
0x14001933f  push    rsi
0x140019340  push    rdi
0x140019341  push    r12
0x140019343  push    r13
0x140019345  push    r14
0x140019347  push    r15
0x140019349  sub     rsp, 58h
0x14001934d  mov     r13, rdx
0x140019350  xorps   xmm0, xmm0
0x140019353  lea     rdx, aDeviceMup; "\\Device\\MUP"
0x14001935a  mov     r8d, 0Bh; MaxCount
0x140019360  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x140019365  mov     rbx, rcx
0x140019368  call    cs:__imp__wcsnicmp
0x14001936e  mov     dword ptr [rsp+98h+arg_10], eax
0x140019375  test    eax, eax
0x140019377  jnz     short loc_1400193E2
0x140019379  mov     rcx, gs:60h
0x140019382  lea     r8d, [rax+10h]; Size
0x140019386  mov     edx, cs:KernelBaseGlobalData; Flags
0x14001938c  mov     rcx, [rcx+30h]; HeapHandle
0x140019390  call    cs:__imp_RtlAllocateHeap
0x140019396  mov     [r13+0], rax
0x14001939a  mov     rcx, rax
0x14001939d  test    rax, rax
0x1400193a0  jnz     short loc_1400193B2
0x1400193a2  lea     ecx, [rax+8]; LastError
0x1400193a5  call    cs:__imp_RtlSetLastWin32Error
0x1400193ab  xor     esi, esi
0x1400193ad  jmp     loc_14001965C
0x1400193b2  movsd   xmm0, qword ptr cs:aUnc_0; "\\\\?\\UNC"
0x1400193ba  movsd   qword ptr [rax], xmm0
0x1400193be  mov     eax, dword ptr cs:aUnc_0+8; "UNC"
0x1400193c4  mov     [rcx+8], eax
0x1400193c7  movzx   eax, word ptr cs:aUnc_0+0Ch; "C"
0x1400193ce  mov     [rcx+0Ch], ax
0x1400193d2  xor     eax, eax
0x1400193d4  mov     [rcx+0Eh], ax
0x1400193d8  mov     eax, 1
0x1400193dd  jmp     loc_14001965E
0x1400193e2  mov     eax, 3
0x1400193e7  mov     [rsp+98h+var_68], 0
0x1400193f0  mov     r8d, eax
0x1400193f3  mov     [rsp+98h+var_70], 80h
0x1400193fb  xor     r9d, r9d
0x1400193fe  mov     dword ptr [rsp+98h+var_78], eax
0x140019402  xor     edx, edx
0x140019404  lea     rcx, aMountpointmana; "\\\\.\\MountPointManager"
0x14001940b  call    CreateFileW
0x140019410  mov     r12, rax
0x140019413  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140019417  jz      short loc_1400193AB
0x140019419  mov     rcx, rbx; Str
0x14001941c  xor     edi, edi
0x14001941e  call    cs:__imp_wcslen
0x140019424  mov     rcx, gs:60h
0x14001942d  mov     edx, cs:KernelBaseGlobalData; Flags
0x140019433  lea     ebp, ds:4[rax*2]
0x14001943a  mov     rcx, [rcx+30h]; HeapHandle
0x14001943e  mov     r8d, ebp; Size
0x140019441  call    cs:__imp_RtlAllocateHeap
0x140019447  mov     r14, rax
0x14001944a  test    rax, rax
0x14001944d  jz      loc_14001960D
0x140019453  mov     rcx, rbx; Str
0x140019456  call    cs:__imp_wcslen
0x14001945c  lea     rcx, [r14+2]; void *
0x140019460  mov     rdx, rbx; Src
0x140019463  add     ax, ax
0x140019466  movzx   r8d, ax; MaxCount
0x14001946a  mov     [r14], r8w
0x14001946e  call    memcpy_0
0x140019473  mov     ebx, 218h
0x140019478  test    rdi, rdi
0x14001947b  jz      short loc_140019495
0x14001947d  mov     rcx, gs:60h
0x140019486  mov     r8, rdi; BaseAddress
0x140019489  xor     edx, edx; Flags
0x14001948b  mov     rcx, [rcx+30h]; HeapHandle
0x14001948f  call    cs:__imp_RtlFreeHeap
0x140019495  mov     rcx, gs:60h
0x14001949e  mov     edx, cs:KernelBaseGlobalData; Flags
0x1400194a4  mov     r8d, ebx; Size
0x1400194a7  mov     rcx, [rcx+30h]; HeapHandle
0x1400194ab  call    cs:__imp_RtlAllocateHeap
0x1400194b1  mov     rdi, rax
0x1400194b4  test    rax, rax
0x1400194b7  jz      loc_14001960D
0x1400194bd  lea     r15, [rax+8]
0x1400194c1  mov     r9d, ebp
0x1400194c4  lea     rcx, [rsp+98h+arg_10]
0x1400194cc  mov     r8, r14
0x1400194cf  mov     [rsp+98h+var_68], rcx; __int64
0x1400194d4  lea     eax, [rbx-8]
0x1400194d7  mov     [rsp+98h+var_70], eax; ULONG
0x1400194db  mov     rcx, r12; Object
0x1400194de  mov     edx, 6D0030h; FsControlCode
0x1400194e3  mov     [rsp+98h+var_78], r15; __int64
0x1400194e8  call    DeviceIoControl
0x1400194ed  mov     esi, eax
0x1400194ef  test    eax, eax
0x1400194f1  jnz     short loc_14001952D
0x1400194f3  mov     ecx, gs:68h
0x1400194fb  cmp     ecx, 0EAh
0x140019501  jnz     short loc_14001950E
0x140019503  mov     ebx, [r15]
0x140019506  add     ebx, 10h
0x140019509  jmp     loc_140019478
0x14001950e  mov     rcx, gs:60h
0x140019517  mov     r8, rdi; BaseAddress
0x14001951a  xor     edx, edx; Flags
0x14001951c  mov     rcx, [rcx+30h]; HeapHandle
0x140019520  call    cs:__imp_RtlFreeHeap
0x140019526  xor     edi, edi
0x140019528  jmp     loc_14001961A
0x14001952d  lea     rdx, [r15+4]; SourceString
0x140019531  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140019536  call    cs:__imp_RtlInitUnicodeString
0x14001953c  cmp     [rsp+98h+DestinationString.Length], 60h ; '`'
0x140019542  mov     cx, 5Ch ; '\'
0x140019546  mov     rax, [rsp+98h+DestinationString.Buffer]
0x14001954b  jz      short loc_14001955F
0x14001954d  cmp     [rsp+98h+DestinationString.Length], 62h ; 'b'
0x140019553  jnz     loc_1400195D9
0x140019559  cmp     [rax+60h], cx
0x14001955d  jnz     short loc_1400195D9
0x14001955f  cmp     [rax], cx
0x140019562  jnz     short loc_1400195D9
0x140019564  cmp     word ptr [rax+2], 3Fh ; '?'
0x140019569  jz      short loc_140019571
0x14001956b  cmp     [rax+2], cx
0x14001956f  jnz     short loc_1400195D9
0x140019571  cmp     word ptr [rax+4], 3Fh ; '?'
0x140019576  jnz     short loc_1400195D9
0x140019578  cmp     [rax+6], cx
0x14001957c  jnz     short loc_1400195D9
0x14001957e  cmp     word ptr [rax+8], 56h ; 'V'
0x140019583  jnz     short loc_1400195D9
0x140019585  cmp     word ptr [rax+0Ah], 6Fh ; 'o'
0x14001958a  jnz     short loc_1400195D9
0x14001958c  cmp     word ptr [rax+0Ch], 6Ch ; 'l'
0x140019591  jnz     short loc_1400195D9
0x140019593  cmp     word ptr [rax+0Eh], 75h ; 'u'
0x140019598  jnz     short loc_1400195D9
0x14001959a  cmp     word ptr [rax+10h], 6Dh ; 'm'
0x14001959f  jnz     short loc_1400195D9
0x1400195a1  cmp     word ptr [rax+12h], 65h ; 'e'
0x1400195a6  jnz     short loc_1400195D9
0x1400195a8  cmp     word ptr [rax+14h], 7Bh ; '{'
0x1400195ad  jnz     short loc_1400195D9
0x1400195af  mov     dx, 2Dh ; '-'
0x1400195b3  cmp     [rax+26h], dx
0x1400195b7  jnz     short loc_1400195D9
0x1400195b9  cmp     [rax+30h], dx
0x1400195bd  jnz     short loc_1400195D9
0x1400195bf  cmp     [rax+3Ah], dx
0x1400195c3  jnz     short loc_1400195D9
0x1400195c5  cmp     [rax+44h], dx
0x1400195c9  jnz     short loc_1400195D9
0x1400195cb  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x1400195d0  jnz     short loc_1400195D9
0x1400195d2  mov     ecx, 3
0x1400195d7  jmp     short loc_140019612
0x1400195d9  mov     eax, [r15]
0x1400195dc  lea     rdx, [r15+4]; Src
0x1400195e0  mov     rcx, 5C003F005C005Ch
0x1400195ea  mov     [r13+0], rdi
0x1400195ee  mov     [rdi], rcx
0x1400195f1  mov     r8d, eax; Size
0x1400195f4  mov     rcx, r15; void *
0x1400195f7  mov     ebx, eax
0x1400195f9  call    memmove_0
0x1400195fe  shr     rbx, 1
0x140019601  xor     eax, eax
0x140019603  mov     [rdi+rbx*2+8], ax
0x140019608  jmp     loc_140019526
0x14001960d  mov     ecx, 8; LastError
0x140019612  call    cs:__imp_RtlSetLastWin32Error
0x140019618  xor     esi, esi
0x14001961a  mov     rcx, r12; Handle
0x14001961d  call    CloseHandle
0x140019622  test    rdi, rdi
0x140019625  jz      short loc_14001963F
0x140019627  mov     rcx, gs:60h
0x140019630  mov     r8, rdi; BaseAddress
0x140019633  xor     edx, edx; Flags
0x140019635  mov     rcx, [rcx+30h]; HeapHandle
0x140019639  call    cs:__imp_RtlFreeHeap
0x14001963f  test    r14, r14
0x140019642  jz      short loc_14001965C
0x140019644  mov     rcx, gs:60h
0x14001964d  mov     r8, r14; BaseAddress
0x140019650  xor     edx, edx; Flags
0x140019652  mov     rcx, [rcx+30h]; HeapHandle
0x140019656  call    cs:__imp_RtlFreeHeap
0x14001965c  mov     eax, esi
0x14001965e  add     rsp, 58h
0x140019662  pop     r15
0x140019664  pop     r14
0x140019666  pop     r13
0x140019668  pop     r12
0x14001966a  pop     rdi
0x14001966b  pop     rsi
0x14001966c  pop     rbp
0x14001966d  pop     rbx
0x14001966e  retn
```
