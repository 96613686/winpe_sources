# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x14000a9ec`
- end: `0x14000ac74`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000a324`

## callees

- `0x140001f94`
- `0x1400021a6`
- `0x14000a680`
- `0x14000a948`
- `0x14000a9ec`
- `0x140010678`
- `0x140010bd8`
- `0x140010c9c`
- `0x14002e3e2`

## import_xrefs

- `msvcrt!_wcslwr` at `0x14000ab82`
- `msvcrt!_wcslwr` at `0x14000ab82`
- `ntdll!RtlAllocateHeap` at `0x14000aa34`
- `ntdll!RtlAllocateHeap` at `0x14000aa5e`
- `ntdll!RtlAllocateHeap` at `0x14000aa34`
- `ntdll!RtlAllocateHeap` at `0x14000aa5e`
- `ntdll!ZwEnumerateKey` at `0x14000ab0a`
- `ntdll!ZwEnumerateKey` at `0x14000ab0a`
- `ntdll!RtlFreeHeap` at `0x14000aac0`
- `ntdll!RtlFreeHeap` at `0x14000abfc`
- `ntdll!RtlFreeHeap` at `0x14000ac19`
- `ntdll!RtlFreeHeap` at `0x14000ac36`
- `ntdll!RtlFreeHeap` at `0x14000aac0`
- `ntdll!RtlFreeHeap` at `0x14000abfc`
- `ntdll!RtlFreeHeap` at `0x14000ac19`
- `ntdll!RtlFreeHeap` at `0x14000ac36`
- `ntdll!ZwClose` at `0x14000aa9f`
- `ntdll!ZwClose` at `0x14000ac45`
- `ntdll!ZwClose` at `0x14000ac54`
- `ntdll!ZwClose` at `0x14000aa9f`
- `ntdll!ZwClose` at `0x14000ac45`
- `ntdll!ZwClose` at `0x14000ac54`

## string_xrefs

- `0x14000aa79`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x14000ab67`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddProfiles(struct _PII_FILTER *this)
{
  wchar_t *v2; // rdi
  wchar_t *Heap; // rsi
  int v4; // ebx
  PVOID v5; // r14
  ULONG i; // r12d
  NTSTATUS v7; // eax
  int v8; // ebx
  int v9; // eax
  wchar_t *v10; // rax
  const unsigned __int16 *v11; // rdx
  wchar_t *String; // [rsp+30h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+48h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+50h] BYREF
  HANDLE KeyHandle; // [rsp+98h] [rbp+58h] BYREF

  ResultLength = 0;
  Handle = 0;
  KeyHandle = 0;
  v2 = 0;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
  if ( Heap )
  {
    v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
    if ( v5 )
    {
      v4 = AslRegistryOpenKey(
             &KeyHandle,
             L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
             8);
      if ( v4 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( Handle )
          {
            ZwClose(Handle);
            Handle = 0;
          }
          if ( v2 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
          String = 0;
          v2 = 0;
          memset_0(v5, 0, 0x218u);
          memset_0(Heap, 0, 0x218u);
          v7 = ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, Heap, 0x217u, &ResultLength);
          if ( v7 == -2147483622 )
            break;
          if ( v7 >= 0 )
          {
            v8 = 0;
            while ( wcsicmp_0(Heap + 8, off_140030EF0[v8]) )
            {
              if ( (unsigned int)++v8 >= 3 )
              {
                if ( (int)AslRegistryOpenSubKey(&Handle) >= 0 )
                {
                  v9 = AslRegistryGetString(&String, Handle, L"ProfileImagePath");
                  v2 = String;
                  if ( v9 >= 0 )
                  {
                    _wcslwr(String);
                    v4 = PiiFilterpAddItemSorted(this, v2, L"%USERPROFILE%");
                    if ( v4 < 0 )
                      goto LABEL_24;
                    v10 = wcsrchr_0(v2, 0x5Cu);
                    if ( v10 )
                    {
                      if ( v10[1] )
                      {
                        v4 = RtlNameValueArray::Insert(
                               (struct _PII_FILTER *)((char *)this + 48),
                               v11,
                               v10 + 1,
                               L"%USERNAME%",
                               *((_QWORD *)this + 8));
                        if ( v4 < 0 )
                          goto LABEL_24;
                      }
                    }
                  }
                }
                break;
              }
            }
          }
        }
        v4 = 0;
      }
    }
    else
    {
      v4 = -1073741801;
    }
LABEL_24:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  else
  {
    v4 = -1073741801;
  }
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000a9ec  mov     [rsp-38h+arg_0], rbx
0x14000a9f1  push    rbp
0x14000a9f2  push    rsi
0x14000a9f3  push    rdi
0x14000a9f4  push    r12
0x14000a9f6  push    r13
0x14000a9f8  push    r14
0x14000a9fa  push    r15
0x14000a9fc  mov     rbp, rsp
0x14000a9ff  sub     rsp, 40h
0x14000aa03  xor     r15d, r15d
0x14000aa06  mov     r13, rcx
0x14000aa09  mov     [rbp+arg_8], r15d
0x14000aa0d  mov     r14d, 218h
0x14000aa13  mov     [rbp+Handle], r15
0x14000aa17  mov     r8d, r14d; Size
0x14000aa1a  mov     [rbp+KeyHandle], r15
0x14000aa1e  mov     edi, r15d
0x14000aa21  mov     rcx, gs:60h
0x14000aa2a  lea     ebx, [r15+8]
0x14000aa2e  mov     edx, ebx; Flags
0x14000aa30  mov     rcx, [rcx+30h]; HeapHandle
0x14000aa34  call    cs:__imp_RtlAllocateHeap
0x14000aa3a  mov     rsi, rax
0x14000aa3d  test    rax, rax
0x14000aa40  jnz     short loc_14000AA4C
0x14000aa42  mov     ebx, 0C0000017h
0x14000aa47  jmp     loc_14000AC1F
0x14000aa4c  mov     rcx, gs:60h
0x14000aa55  mov     r8, r14; Size
0x14000aa58  mov     edx, ebx; Flags
0x14000aa5a  mov     rcx, [rcx+30h]; HeapHandle
0x14000aa5e  call    cs:__imp_RtlAllocateHeap
0x14000aa64  mov     r14, rax
0x14000aa67  test    rax, rax
0x14000aa6a  jnz     short loc_14000AA76
0x14000aa6c  mov     ebx, 0C0000017h
0x14000aa71  jmp     loc_14000ABEA
0x14000aa76  mov     r8d, ebx
0x14000aa79  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x14000aa80  lea     rcx, [rbp+KeyHandle]
0x14000aa84  call    AslRegistryOpenKey
0x14000aa89  mov     ebx, eax
0x14000aa8b  test    eax, eax
0x14000aa8d  js      loc_14000ABEA
0x14000aa93  mov     r12d, r15d
0x14000aa96  mov     rcx, [rbp+Handle]; Handle
0x14000aa9a  test    rcx, rcx
0x14000aa9d  jz      short loc_14000AAA9
0x14000aa9f  call    cs:__imp_ZwClose
0x14000aaa5  mov     [rbp+Handle], r15
0x14000aaa9  test    rdi, rdi
0x14000aaac  jz      short loc_14000AAC6
0x14000aaae  mov     rcx, gs:60h
0x14000aab7  mov     r8, rdi; P
0x14000aaba  xor     edx, edx; Flags
0x14000aabc  mov     rcx, [rcx+30h]; HeapHandle
0x14000aac0  call    cs:__imp_RtlFreeHeap
0x14000aac6  mov     ebx, 218h
0x14000aacb  mov     [rbp+String], r15
0x14000aacf  mov     r8d, ebx; Size
0x14000aad2  xor     edx, edx; Val
0x14000aad4  mov     rcx, r14; void *
0x14000aad7  mov     rdi, r15
0x14000aada  call    memset_0
0x14000aadf  mov     r8d, ebx; Size
0x14000aae2  xor     edx, edx; Val
0x14000aae4  mov     rcx, rsi; void *
0x14000aae7  call    memset_0
0x14000aaec  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000aaf0  lea     rax, [rbp+arg_8]
0x14000aaf4  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14000aaf9  mov     r9, rsi; KeyInformation
0x14000aafc  xor     r8d, r8d; KeyInformationClass
0x14000aaff  mov     [rsp+40h+Length], 217h; Length
0x14000ab07  mov     edx, r12d; Index
0x14000ab0a  call    cs:__imp_ZwEnumerateKey
0x14000ab10  cmp     eax, 8000001Ah
0x14000ab15  jz      loc_14000ABE7
0x14000ab1b  test    eax, eax
0x14000ab1d  js      loc_14000ABDF
0x14000ab23  mov     ebx, r15d
0x14000ab26  lea     rax, off_140030EF0; "s-1-5-18"
0x14000ab2d  mov     edx, ebx
0x14000ab2f  lea     rcx, [rsi+10h]; String1
0x14000ab33  mov     rdx, [rax+rdx*8]; String2
0x14000ab37  call    _wcsicmp_0
0x14000ab3c  test    eax, eax
0x14000ab3e  jz      loc_14000ABDC
0x14000ab44  inc     ebx
0x14000ab46  cmp     ebx, 3
0x14000ab49  jb      short loc_14000AB26
0x14000ab4b  mov     rdx, [rbp+KeyHandle]
0x14000ab4f  lea     r8, [rsi+10h]
0x14000ab53  lea     rcx, [rbp+Handle]; KeyHandle
0x14000ab57  call    AslRegistryOpenSubKey
0x14000ab5c  xor     r15d, r15d
0x14000ab5f  test    eax, eax
0x14000ab61  js      short loc_14000ABDF
0x14000ab63  mov     rdx, [rbp+Handle]
0x14000ab67  lea     r8, aProfileimagepa; "ProfileImagePath"
0x14000ab6e  lea     rcx, [rbp+String]
0x14000ab72  call    AslRegistryGetString
0x14000ab77  mov     rdi, [rbp+String]
0x14000ab7b  test    eax, eax
0x14000ab7d  js      short loc_14000ABDF
0x14000ab7f  mov     rcx, rdi; String
0x14000ab82  call    cs:__imp__wcslwr
0x14000ab88  lea     r8, aUserprofile; "%USERPROFILE%"
0x14000ab8f  mov     rdx, rdi; unsigned __int16 *
0x14000ab92  mov     rcx, r13; this
0x14000ab95  call    ?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z; PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)
0x14000ab9a  mov     ebx, eax
0x14000ab9c  test    eax, eax
0x14000ab9e  js      short loc_14000ABEA
0x14000aba0  lea     edx, [r15+5Ch]; Ch
0x14000aba4  mov     rcx, rdi; Str
0x14000aba7  call    wcsrchr_0
0x14000abac  test    rax, rax
0x14000abaf  jz      short loc_14000ABDF
0x14000abb1  lea     r8, [rax+2]; unsigned __int16 *
0x14000abb5  cmp     [r8], r15w
0x14000abb9  jz      short loc_14000ABDF
0x14000abbb  lea     rcx, [r13+30h]; this
0x14000abbf  mov     rax, [rcx+10h]
0x14000abc3  lea     r9, aUsername; "%USERNAME%"
0x14000abca  mov     qword ptr [rsp+40h+Length], rax; unsigned __int64
0x14000abcf  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x14000abd4  mov     ebx, eax
0x14000abd6  test    eax, eax
0x14000abd8  js      short loc_14000ABEA
0x14000abda  jmp     short loc_14000ABDF
0x14000abdc  xor     r15d, r15d
0x14000abdf  inc     r12d
0x14000abe2  jmp     loc_14000AA96
0x14000abe7  mov     ebx, r15d
0x14000abea  mov     rcx, gs:60h
0x14000abf3  mov     r8, rsi; P
0x14000abf6  xor     edx, edx; Flags
0x14000abf8  mov     rcx, [rcx+30h]; HeapHandle
0x14000abfc  call    cs:__imp_RtlFreeHeap
0x14000ac02  test    r14, r14
0x14000ac05  jz      short loc_14000AC1F
0x14000ac07  mov     rcx, gs:60h
0x14000ac10  mov     r8, r14; P
0x14000ac13  xor     edx, edx; Flags
0x14000ac15  mov     rcx, [rcx+30h]; HeapHandle
0x14000ac19  call    cs:__imp_RtlFreeHeap
0x14000ac1f  test    rdi, rdi
0x14000ac22  jz      short loc_14000AC3C
0x14000ac24  mov     rcx, gs:60h
0x14000ac2d  mov     r8, rdi; P
0x14000ac30  xor     edx, edx; Flags
0x14000ac32  mov     rcx, [rcx+30h]; HeapHandle
0x14000ac36  call    cs:__imp_RtlFreeHeap
0x14000ac3c  mov     rcx, [rbp+KeyHandle]; Handle
0x14000ac40  test    rcx, rcx
0x14000ac43  jz      short loc_14000AC4B
0x14000ac45  call    cs:__imp_ZwClose
0x14000ac4b  mov     rcx, [rbp+Handle]; Handle
0x14000ac4f  test    rcx, rcx
0x14000ac52  jz      short loc_14000AC5A
0x14000ac54  call    cs:__imp_ZwClose
0x14000ac5a  mov     eax, ebx
0x14000ac5c  mov     rbx, [rsp+40h+arg_0]
0x14000ac64  add     rsp, 40h
0x14000ac68  pop     r15
0x14000ac6a  pop     r14
0x14000ac6c  pop     r13
0x14000ac6e  pop     r12
0x14000ac70  pop     rdi
0x14000ac71  pop     rsi
0x14000ac72  pop     rbp
0x14000ac73  retn
```
