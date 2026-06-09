# SclRegEnumerateHiveList

- ea: `0x180008ff0`
- end: `0x180009116`
- name: `SclRegEnumerateHiveList`
- size: `294`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800092bc`
- `0x180009904`

## callees

- `0x1800014e8`
- `0x180008ff0`
- `0x18000911c`
- `0x18000923c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000904d`
- `ntdll!RtlAllocateHeap` at `0x18000904d`
- `ntdll!NtClose` at `0x180009079`
- `ntdll!NtClose` at `0x180009079`
- `ntdll!RtlFreeHeap` at `0x180009096`
- `ntdll!RtlFreeHeap` at `0x180009096`

## string_xrefs

- `0x18000900f`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\HIVELIST`

## pseudocode

```c
__int64 __fastcall SclRegEnumerateHiveList(__int64 a1, __int64 a2)
{
  unsigned int *v3; // rbx
  int Key; // eax
  unsigned int *v5; // rdi
  unsigned int v6; // esi
  int v8; // edi
  unsigned int *Heap; // [rsp+30h] [rbp-10h] BYREF
  int v10; // [rsp+60h] [rbp+20h] BYREF
  int v11; // [rsp+64h] [rbp+24h]
  int v12; // [rsp+70h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+38h] BYREF

  v11 = HIDWORD(a1);
  Handle = 0;
  v10 = 0;
  v3 = 0;
  Key = SclCreateKey(
          0,
          L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\HIVELIST",
          0x20019u,
          (__int64)&Handle);
  if ( Key < 0 )
    goto LABEL_4;
  v10 = 4120;
  Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x1018u);
  v3 = Heap;
  if ( !Heap )
  {
    Key = -1073741801;
LABEL_4:
    v5 = 0;
    goto LABEL_5;
  }
  v8 = 0;
  do
  {
    v12 = 0;
    Key = SclRegEnumerateValueKey((_DWORD)Handle, v8, 1, (unsigned int)&Heap, (__int64)&v10, (__int64)&v12);
    v3 = Heap;
    if ( Key >= 0 )
      Key = SclRegEnumerateHiveList_Callback(
              a2,
              Heap + 5,
              (unsigned __int64)Heap[4] >> 1,
              (char *)Heap + Heap[2],
              (unsigned __int64)Heap[3] >> 1);
    ++v8;
  }
  while ( Key >= 0 );
  v5 = v3;
LABEL_5:
  v6 = 0;
  if ( Key != -2147483622 )
    v6 = Key;
  if ( Handle )
    NtClose(Handle);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  return v6;
}

```

## disassembly

```asm
0x180008ff0  mov     [rsp-18h+arg_8], rbx
0x180008ff5  mov     [rsp-18h+arg_0], rcx
0x180008ffa  push    rbp
0x180008ffb  push    rsi
0x180008ffc  push    rdi
0x180008ffd  mov     rbp, rsp
0x180009000  sub     rsp, 40h
0x180009004  mov     rsi, rdx
0x180009007  mov     [rbp+Handle], 0
0x18000900f  lea     rdx, aRegistryMachin_3; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x180009016  mov     dword ptr [rbp+arg_0], 0
0x18000901d  lea     r9, [rbp+Handle]
0x180009021  mov     r8d, 20019h
0x180009027  xor     ecx, ecx
0x180009029  xor     ebx, ebx
0x18000902b  call    SclCreateKey
0x180009030  test    eax, eax
0x180009032  js      short loc_180009064
0x180009034  mov     rcx, gs:60h
0x18000903d  mov     r8d, 1018h; Size
0x180009043  xor     edx, edx; Flags
0x180009045  mov     dword ptr [rbp+arg_0], r8d
0x180009049  mov     rcx, [rcx+30h]; HeapHandle
0x18000904d  call    cs:__imp_RtlAllocateHeap
0x180009053  mov     [rbp+var_10], rax
0x180009057  mov     rbx, rax
0x18000905a  test    rax, rax
0x18000905d  jnz     short loc_1800090AB
0x18000905f  mov     eax, 0C0000017h
0x180009064  xor     edi, edi
0x180009066  mov     rcx, [rbp+Handle]; Handle
0x18000906a  xor     esi, esi
0x18000906c  cmp     eax, 8000001Ah
0x180009071  cmovnz  esi, eax
0x180009074  test    rcx, rcx
0x180009077  jz      short loc_18000907F
0x180009079  call    cs:__imp_NtClose
0x18000907f  test    rdi, rdi
0x180009082  jz      short loc_18000909C
0x180009084  mov     rcx, gs:60h
0x18000908d  mov     r8, rbx; P
0x180009090  xor     edx, edx; Flags
0x180009092  mov     rcx, [rcx+30h]; HeapHandle
0x180009096  call    cs:__imp_RtlFreeHeap
0x18000909c  mov     rbx, [rsp+40h+arg_8]
0x1800090a1  mov     eax, esi
0x1800090a3  add     rsp, 40h
0x1800090a7  pop     rdi
0x1800090a8  pop     rsi
0x1800090a9  pop     rbp
0x1800090aa  retn
0x1800090ab  xor     edi, edi
0x1800090ad  mov     rcx, [rbp+Handle]
0x1800090b1  lea     rax, [rbp+arg_10]
0x1800090b5  mov     [rsp+40h+var_18], rax
0x1800090ba  lea     r9, [rbp+var_10]
0x1800090be  lea     rax, [rbp+arg_0]
0x1800090c2  mov     [rbp+arg_10], 0
0x1800090c9  mov     r8d, 1
0x1800090cf  mov     [rsp+40h+var_20], rax
0x1800090d4  mov     edx, edi
0x1800090d6  call    SclRegEnumerateValueKey
0x1800090db  mov     rbx, [rbp+var_10]
0x1800090df  test    eax, eax
0x1800090e1  js      short loc_180009108
0x1800090e3  mov     eax, [rbx+0Ch]
0x1800090e6  lea     rdx, [rbx+14h]
0x1800090ea  mov     r9d, [rbx+8]
0x1800090ee  mov     rcx, rsi
0x1800090f1  mov     r8d, [rbx+10h]
0x1800090f5  add     r9, rbx
0x1800090f8  shr     rax, 1
0x1800090fb  shr     r8, 1
0x1800090fe  mov     [rsp+40h+var_20], rax
0x180009103  call    SclRegEnumerateHiveList_Callback
0x180009108  inc     edi
0x18000910a  test    eax, eax
0x18000910c  jns     short loc_1800090AD
0x18000910e  mov     rdi, rbx
0x180009111  jmp     loc_180009066
```
