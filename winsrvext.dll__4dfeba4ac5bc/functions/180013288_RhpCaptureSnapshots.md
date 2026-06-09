# RhpCaptureSnapshots

- ea: `0x180013288`
- end: `0x1800133dd`
- name: `RhpCaptureSnapshots`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012ef8`

## callees

- `0x180013288`
- `0x1800138c5`

## import_xrefs

- `ntdll!NtOpenProcess` at `0x180013365`
- `ntdll!NtOpenProcess` at `0x180013365`
- `ntdll!NtClose` at `0x1800133ae`
- `ntdll!NtClose` at `0x1800133ae`
- `ntdll!RtlGetNtProductType` at `0x180013305`
- `ntdll!RtlGetNtProductType` at `0x180013305`
- `ntdll!PssNtCaptureSnapshot` at `0x18001339a`
- `ntdll!PssNtCaptureSnapshot` at `0x18001339a`

## pseudocode

```c
int __fastcall RhpCaptureSnapshots(_QWORD *a1, _OWORD *a2, __m128i *a3, _NT_PRODUCT_TYPE a4, int *a5)
{
  unsigned __int64 v8; // rax
  __m128i si128; // xmm1
  int *v10; // rbx
  void *v11; // rdx
  int v12; // eax
  void *v13; // rcx
  int v14; // ebx
  void *ProcessHandle; // [rsp+20h] [rbp-20h] BYREF
  __int64 v17; // [rsp+28h] [rbp-18h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+30h] [rbp-10h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+78h] [rbp+38h] BYREF

  ProductType = a4;
  ProcessHandle = 0;
  v17 = 0;
  ClientId = 0;
  LODWORD(v8) = (unsigned int)memset_0(a1, 0, 0x80u);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v10 = a5;
  *a2 = 0;
  *a3 = si128;
  a3[1] = si128;
  a3[2] = si128;
  a3[3] = si128;
  if ( *v10 )
  {
    ProductType = 0;
    if ( !RtlGetNtProductType(&ProductType) || ProductType != NtProductWinNt )
      goto LABEL_8;
    v8 = MEMORY[0x7FFE0310];
    if ( !MEMORY[0x7FFE0310] )
      v8 = MEMORY[0x7FFE02E8];
    if ( v8 <= 0x83400 )
    {
      a3->m128i_i32[0] = -1073741801;
    }
    else
    {
LABEL_8:
      ClientId.UniqueProcess = (HANDLE)*v10;
      ClientId.UniqueThread = 0;
      LODWORD(v8) = NtOpenProcess(&ProcessHandle, 0x4D0u, (POBJECT_ATTRIBUTES)&ObjectAttributes, &ClientId);
      a3->m128i_i32[0] = v8;
      if ( (v8 & 0x80000000) == 0LL )
      {
        v11 = ProcessHandle;
        *a1 = 0;
        v17 = 0;
        v12 = PssNtCaptureSnapshot(&v17, v11, 3690994175LL, 1048607);
        v13 = ProcessHandle;
        v14 = v12;
        a3->m128i_i32[0] = v12;
        LODWORD(v8) = NtClose(v13);
        if ( v14 >= 0 )
        {
          LODWORD(v8) = v17;
          *a1 = v17;
          *(_BYTE *)a2 = 8;
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180013288  mov     [rsp-18h+arg_0], rbx
0x18001328d  mov     [rsp-18h+arg_8], rsi
0x180013292  mov     [rsp-18h+ProductType], r9d
0x180013297  push    rbp
0x180013298  push    rdi
0x180013299  push    r14
0x18001329b  mov     rbp, rsp
0x18001329e  sub     rsp, 40h
0x1800132a2  mov     rdi, r8
0x1800132a5  mov     [rbp+ProcessHandle], 0
0x1800132ad  mov     r14, rdx
0x1800132b0  mov     [rbp+var_18], 0
0x1800132b8  xorps   xmm0, xmm0
0x1800132bb  xor     edx, edx; Val
0x1800132bd  mov     r8d, 80h; Size
0x1800132c3  mov     rsi, rcx
0x1800132c6  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x1800132ca  call    memset_0
0x1800132cf  movdqa  xmm1, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800132d7  xorps   xmm0, xmm0
0x1800132da  mov     rbx, [rbp+arg_20]
0x1800132de  movups  xmmword ptr [r14], xmm0
0x1800132e2  movups  xmmword ptr [rdi], xmm1
0x1800132e5  movups  xmmword ptr [rdi+10h], xmm1
0x1800132e9  movups  xmmword ptr [rdi+20h], xmm1
0x1800132ed  movups  xmmword ptr [rdi+30h], xmm1
0x1800132f1  cmp     dword ptr [rbx], 0
0x1800132f4  jz      loc_1800133C9
0x1800132fa  lea     rcx, [rbp+ProductType]; ProductType
0x1800132fe  mov     [rbp+ProductType], 0
0x180013305  call    cs:__imp_RtlGetNtProductType
0x18001330c  nop     dword ptr [rax+rax+00h]
0x180013311  test    al, al
0x180013313  jz      short loc_180013342
0x180013315  cmp     [rbp+ProductType], 1
0x180013319  jnz     short loc_180013342
0x18001331b  mov     rax, ds:7FFE0310h
0x180013323  test    rax, rax
0x180013326  jnz     short loc_18001332F
0x180013328  mov     eax, ds:7FFE02E8h
0x18001332f  cmp     rax, 83400h
0x180013335  ja      short loc_180013342
0x180013337  mov     dword ptr [rdi], 0C0000017h
0x18001333d  jmp     loc_1800133C9
0x180013342  movsxd  rax, dword ptr [rbx]
0x180013345  lea     r9, [rbp+ClientId]; ClientId
0x180013349  lea     r8, ObjectAttributes; ObjectAttributes
0x180013350  mov     [rbp+ClientId.UniqueProcess], rax
0x180013354  mov     edx, 4D0h; DesiredAccess
0x180013359  mov     [rbp+ClientId.UniqueThread], 0
0x180013361  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x180013365  call    cs:__imp_NtOpenProcess
0x18001336c  nop     dword ptr [rax+rax+00h]
0x180013371  mov     [rdi], eax
0x180013373  test    eax, eax
0x180013375  js      short loc_1800133C9
0x180013377  mov     rdx, [rbp+ProcessHandle]
0x18001337b  lea     rcx, [rbp+var_18]
0x18001337f  mov     r9d, 10001Fh
0x180013385  mov     qword ptr [rsi], 0
0x18001338c  mov     r8d, 0DC0019FFh
0x180013392  mov     [rbp+var_18], 0
0x18001339a  call    cs:__imp_PssNtCaptureSnapshot
0x1800133a1  nop     dword ptr [rax+rax+00h]
0x1800133a6  mov     rcx, [rbp+ProcessHandle]; Handle
0x1800133aa  mov     ebx, eax
0x1800133ac  mov     [rdi], eax
0x1800133ae  call    cs:__imp_NtClose
0x1800133b5  nop     dword ptr [rax+rax+00h]
0x1800133ba  test    ebx, ebx
0x1800133bc  js      short loc_1800133C9
0x1800133be  mov     rax, [rbp+var_18]
0x1800133c2  mov     [rsi], rax
0x1800133c5  mov     byte ptr [r14], 8
0x1800133c9  mov     rbx, [rsp+40h+arg_0]
0x1800133ce  mov     rsi, [rsp+40h+arg_8]
0x1800133d3  add     rsp, 40h
0x1800133d7  pop     r14
0x1800133d9  pop     rdi
0x1800133da  pop     rbp
0x1800133db  retn
```
