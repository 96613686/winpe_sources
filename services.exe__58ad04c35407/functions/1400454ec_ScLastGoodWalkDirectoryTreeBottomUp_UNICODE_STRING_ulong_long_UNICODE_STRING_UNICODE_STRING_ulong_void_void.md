# ScLastGoodWalkDirectoryTreeBottomUp(_UNICODE_STRING *,ulong,long (*)(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *),void *)

- ea: `0x1400454ec`
- end: `0x1400456fd`
- name: `?ScLastGoodWalkDirectoryTreeBottomUp@@YAKPEAU_UNICODE_STRING@@KP6AJ00KPEAX@Z1@Z`
- size: `529`
- prototype: `ULONG __fastcall(PCUNICODE_STRING SourceString, __int64, int (*)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x14007f1dc`

## callees

- `0x1400454ec`
- `0x140045704`
- `0x1400575b0`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x1400455b4`
- `ntdll!RtlCopyUnicodeString` at `0x1400455b4`
- `ntdll!RtlNtStatusToDosError` at `0x14004556f`
- `ntdll!RtlNtStatusToDosError` at `0x14004556f`
- `ntdll!RtlFreeHeap` at `0x140045698`
- `ntdll!RtlFreeHeap` at `0x1400456e7`
- `ntdll!RtlFreeHeap` at `0x140045698`
- `ntdll!RtlFreeHeap` at `0x1400456e7`
- `ntdll!RtlAllocateHeap` at `0x14004555c`
- `ntdll!RtlAllocateHeap` at `0x14004555c`

## pseudocode

```c
ULONG __fastcall ScLastGoodWalkDirectoryTreeBottomUp(
        PCUNICODE_STRING SourceString,
        __int64 a2,
        int (*a3)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *),
        void *a4)
{
  __int64 Length; // r8
  struct _UNICODE_STRING *Heap; // rax
  struct _UNICODE_STRING *v7; // rbx
  NTSTATUS v8; // ecx
  void *v10; // r9
  struct _LIST_ENTRY *Flink; // rax
  int v12; // edi
  struct _UNICODE_STRING *Blink; // rbx
  struct _LIST_ENTRY *v14; // rax
  struct _LIST_ENTRY *v15; // r8
  struct _LIST_ENTRY *v16; // rax
  unsigned int v17; // [rsp+28h] [rbp-D8h]
  struct _LIST_ENTRY v18; // [rsp+40h] [rbp-C0h] BYREF
  struct _LIST_ENTRY v19; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE FileInformation[1024]; // [rsp+60h] [rbp-A0h] BYREF

  Length = SourceString->Length;
  v18.Blink = &v18;
  v18.Flink = &v18;
  v19.Blink = &v19;
  v19.Flink = &v19;
  Heap = (struct _UNICODE_STRING *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length + 38);
  v7 = Heap;
  if ( Heap )
  {
    Heap[1].Length = 0;
    Heap[1].MaximumLength = SourceString->Length;
    Heap[1].Buffer = &Heap[2].Length;
    RtlCopyUnicodeString(Heap + 1, SourceString);
    Flink = v18.Flink;
    if ( v18.Flink->Blink != &v18 )
LABEL_20:
      __fastfail(3u);
    *(_QWORD *)&v7->Length = v18.Flink;
    v7->Buffer = (PWSTR)&v18;
    v12 = 0;
    Flink->Blink = (struct _LIST_ENTRY *)v7;
    v18.Flink = (struct _LIST_ENTRY *)v7;
    while ( v7 != (struct _UNICODE_STRING *)&v18 )
    {
      v12 = ScpLastGoodWalkDirectoryTreeHelper(v7 + 1, 8u, 0, v10, FileInformation, v17, &v18);
      if ( v12 < 0 )
        break;
      v7 = *(struct _UNICODE_STRING **)&v7->Length;
    }
    while ( v18.Flink != &v18 )
    {
      if ( v12 < 0 )
        goto LABEL_15;
      Blink = (struct _UNICODE_STRING *)v18.Blink;
      if ( v18.Blink->Flink != &v18 )
        goto LABEL_20;
      v14 = v18.Blink->Blink;
      if ( v14->Flink != v18.Blink )
        goto LABEL_20;
      v18.Blink = v18.Blink->Blink;
      v14->Flink = &v18;
      v12 = ScpLastGoodWalkDirectoryTreeHelper(
              Blink + 1,
              7u,
              (int (*)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *))ScpLastGoodDeleteFiles,
              v10,
              FileInformation,
              v17,
              &v19);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Blink);
    }
    if ( v12 < 0 )
    {
LABEL_15:
      while ( 1 )
      {
        v15 = v18.Flink;
        if ( v18.Flink == &v18 )
          break;
        if ( v18.Flink->Blink != &v18 )
          goto LABEL_20;
        v16 = v18.Flink->Flink;
        if ( v18.Flink->Flink->Blink != v18.Flink )
          goto LABEL_20;
        v18.Flink = v18.Flink->Flink;
        v16->Blink = &v18;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      }
    }
    v8 = v12;
  }
  else
  {
    v8 = -1073741670;
  }
  return RtlNtStatusToDosError(v8);
}

```

## disassembly

```asm
0x1400454ec  mov     [rsp-8+arg_8], rbx
0x1400454f1  mov     [rsp-8+arg_10], rdi
0x1400454f6  push    rbp
0x1400454f7  lea     rbp, [rsp-370h]
0x1400454ff  sub     rsp, 470h
0x140045506  mov     rax, cs:__security_cookie
0x14004550d  xor     rax, rsp
0x140045510  mov     [rbp+370h+var_10], rax
0x140045517  movzx   r8d, word ptr [rcx]
0x14004551b  lea     rax, [rsp+470h+var_430]
0x140045520  mov     [rsp+470h+P], rax
0x140045525  mov     rdi, rcx
0x140045528  lea     rax, [rsp+470h+var_430]
0x14004552d  add     r8, 26h ; '&'; Size
0x140045531  mov     [rsp+470h+var_430], rax
0x140045536  mov     edx, 8; Flags
0x14004553b  lea     rax, [rsp+470h+var_420]
0x140045540  mov     [rsp+470h+var_420.Blink], rax
0x140045545  lea     rax, [rsp+470h+var_420]
0x14004554a  mov     [rsp+470h+var_420.Flink], rax
0x14004554f  mov     rcx, gs:60h
0x140045558  mov     rcx, [rcx+30h]; HeapHandle
0x14004555c  call    cs:__imp_RtlAllocateHeap
0x140045562  mov     rbx, rax
0x140045565  test    rax, rax
0x140045568  jnz     short loc_140045599
0x14004556a  mov     ecx, 0C000009Ah; Status
0x14004556f  call    cs:__imp_RtlNtStatusToDosError
0x140045575  mov     rcx, [rbp+370h+var_10]
0x14004557c  xor     rcx, rsp; StackCookie
0x14004557f  call    __security_check_cookie
0x140045584  lea     r11, [rsp+470h+var_s0]
0x14004558c  mov     rbx, [r11+18h]
0x140045590  mov     rdi, [r11+20h]
0x140045594  mov     rsp, r11
0x140045597  pop     rbp
0x140045598  retn
0x140045599  lea     rcx, [rax+10h]; DestinationString
0x14004559d  mov     rdx, rdi; SourceString
0x1400455a0  xor     eax, eax
0x1400455a2  mov     [rcx], ax
0x1400455a5  movzx   eax, word ptr [rdi]
0x1400455a8  mov     [rbx+12h], ax
0x1400455ac  lea     rax, [rbx+20h]
0x1400455b0  mov     [rbx+18h], rax
0x1400455b4  call    cs:__imp_RtlCopyUnicodeString
0x1400455ba  mov     rax, [rsp+470h+var_430]
0x1400455bf  lea     rcx, [rsp+470h+var_430]
0x1400455c4  cmp     [rax+8], rcx
0x1400455c8  jnz     loc_1400456F6
0x1400455ce  mov     [rbx], rax
0x1400455d1  lea     rcx, [rsp+470h+var_430]
0x1400455d6  mov     [rbx+8], rcx
0x1400455da  xor     edi, edi
0x1400455dc  mov     [rax+8], rbx
0x1400455e0  mov     [rsp+470h+var_430], rbx
0x1400455e5  jmp     short loc_140045614
0x1400455e7  xor     r8d, r8d; int (*)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *)
0x1400455ea  lea     rax, [rsp+470h+var_430]
0x1400455ef  mov     [rsp+470h+var_440], rax; struct _LIST_ENTRY *
0x1400455f4  lea     rcx, [rbx+10h]; struct _UNICODE_STRING *
0x1400455f8  lea     rax, [rsp+470h+var_410]
0x1400455fd  mov     [rsp+470h+FileInformation], rax; FileInformation
0x140045602  lea     edx, [r8+8]; unsigned int
0x140045606  call    ?ScpLastGoodWalkDirectoryTreeHelper@@YAJPEAU_UNICODE_STRING@@KP6AJ00KPEAX@Z1PEAEKPEAU_LIST_ENTRY@@@Z; ScpLastGoodWalkDirectoryTreeHelper(_UNICODE_STRING *,ulong,long (*)(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *),void *,uchar *,ulong,_LIST_ENTRY *)
0x14004560b  mov     edi, eax
0x14004560d  test    eax, eax
0x14004560f  js      short loc_14004561E
0x140045611  mov     rbx, [rbx]
0x140045614  lea     rax, [rsp+470h+var_430]
0x140045619  cmp     rbx, rax
0x14004561c  jnz     short loc_1400455E7
0x14004561e  lea     rax, [rsp+470h+var_430]
0x140045623  cmp     [rsp+470h+var_430], rax
0x140045628  jz      short loc_1400456A3
0x14004562a  test    edi, edi
0x14004562c  js      short loc_1400456A7
0x14004562e  mov     rbx, [rsp+470h+P]
0x140045633  lea     rax, [rsp+470h+var_430]
0x140045638  cmp     [rbx], rax
0x14004563b  jnz     loc_1400456F6
0x140045641  mov     rax, [rbx+8]
0x140045645  cmp     [rax], rbx
0x140045648  jnz     loc_1400456F6
0x14004564e  mov     [rsp+470h+P], rax
0x140045653  lea     rcx, [rsp+470h+var_430]
0x140045658  mov     [rax], rcx
0x14004565b  lea     r8, ?ScpLastGoodDeleteFiles@@YAJPEAU_UNICODE_STRING@@0KPEAX@Z; int (*)(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *)
0x140045662  lea     rax, [rsp+470h+var_420]
0x140045667  mov     edx, 7; unsigned int
0x14004566c  mov     [rsp+470h+var_440], rax; struct _LIST_ENTRY *
0x140045671  lea     rcx, [rbx+10h]; struct _UNICODE_STRING *
0x140045675  lea     rax, [rsp+470h+var_410]
0x14004567a  mov     [rsp+470h+FileInformation], rax; FileInformation
0x14004567f  call    ?ScpLastGoodWalkDirectoryTreeHelper@@YAJPEAU_UNICODE_STRING@@KP6AJ00KPEAX@Z1PEAEKPEAU_LIST_ENTRY@@@Z; ScpLastGoodWalkDirectoryTreeHelper(_UNICODE_STRING *,ulong,long (*)(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *),void *,uchar *,ulong,_LIST_ENTRY *)
0x140045684  mov     rcx, gs:60h
0x14004568d  mov     r8, rbx; P
0x140045690  xor     edx, edx; Flags
0x140045692  mov     edi, eax
0x140045694  mov     rcx, [rcx+30h]; HeapHandle
0x140045698  call    cs:__imp_RtlFreeHeap
0x14004569e  jmp     loc_14004561E
0x1400456a3  test    edi, edi
0x1400456a5  jns     short loc_1400456EF
0x1400456a7  mov     r8, [rsp+470h+var_430]; P
0x1400456ac  lea     rax, [rsp+470h+var_430]
0x1400456b1  cmp     r8, rax
0x1400456b4  jz      short loc_1400456EF
0x1400456b6  lea     rax, [rsp+470h+var_430]
0x1400456bb  cmp     [r8+8], rax
0x1400456bf  jnz     short loc_1400456F6
0x1400456c1  mov     rax, [r8]
0x1400456c4  cmp     [rax+8], r8
0x1400456c8  jnz     short loc_1400456F6
0x1400456ca  mov     [rsp+470h+var_430], rax
0x1400456cf  lea     rcx, [rsp+470h+var_430]
0x1400456d4  mov     [rax+8], rcx
0x1400456d8  xor     edx, edx; Flags
0x1400456da  mov     rcx, gs:60h
0x1400456e3  mov     rcx, [rcx+30h]; HeapHandle
0x1400456e7  call    cs:__imp_RtlFreeHeap
0x1400456ed  jmp     short loc_1400456A7
0x1400456ef  mov     ecx, edi
0x1400456f1  jmp     loc_14004556F
0x1400456f6  mov     ecx, 3
0x1400456fb  int     29h; Win8: RtlFailFast(ecx)
```
