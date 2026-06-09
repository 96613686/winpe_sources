# WcPrePopulatePath

- ea: `0x14001939c`
- end: `0x140019549`
- name: `WcPrePopulatePath`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140018e28`

## callees

- `0x140007c60`
- `0x14001939c`
- `0x140026210`
- `0x14002d790`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140019507`
- `ntoskrnl!ObfDereferenceObject` at `0x14001951c`
- `ntoskrnl!ObfDereferenceObject` at `0x140019507`
- `ntoskrnl!ObfDereferenceObject` at `0x14001951c`
- `FLTMGR!FltClose` at `0x1400194f2`
- `FLTMGR!FltClose` at `0x1400194f2`

## pseudocode

```c
__int64 __fastcall WcPrePopulatePath(
        struct _FLT_CALLBACK_DATA *a1,
        __int64 a2,
        unsigned int a3,
        struct _FLT_FILE_NAME_INFORMATION *a4)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  int v5; // ebx
  char v7; // r9
  ULONG v11; // edi
  struct _FLT_INSTANCE *v12; // rcx
  int v13; // eax
  char v15[4]; // [rsp+50h] [rbp-49h] BYREF
  int v16; // [rsp+54h] [rbp-45h] BYREF
  int v17; // [rsp+58h] [rbp-41h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp-39h] BYREF
  PVOID Object; // [rsp+68h] [rbp-31h] BYREF
  PVOID v20; // [rsp+70h] [rbp-29h] BYREF
  __int64 v21[2]; // [rsp+78h] [rbp-21h] BYREF
  _OWORD v22[3]; // [rsp+88h] [rbp-11h] BYREF

  Iopb = a1->Iopb;
  v5 = 0;
  FileHandle = 0;
  Object = 0;
  v7 = 0;
  v16 = 0;
  v15[0] = 0;
  memset(v22, 0, sizeof(v22));
  v20 = 0;
  v17 = 0;
  *(_OWORD *)v21 = 0;
  v11 = Iopb->Parameters.Create.Options & 0x41 | 0x28;
  while ( !v7 )
  {
    v12 = *(struct _FLT_INSTANCE **)(a2 + 24);
    *(_QWORD *)&v22[0] = v21;
    *(_QWORD *)&v22[1] = a3 | 0x8000000400000000uLL;
    *((_QWORD *)&v22[0] + 1) = v21;
    v21[0] = (__int64)v22;
    DWORD2(v22[2]) = 48;
    v21[1] = (__int64)v22;
    *(_OWORD *)((char *)&v22[1] + 8) = 0;
    v13 = WcOpenReparsePoint(v12, &a4->Name, 0, 0, 0x80u, v11, 7u, (PVOID **)v21, &FileHandle, (PFILE_OBJECT *)&Object);
    v5 = v13;
    if ( (BYTE4(v22[1]) & 1) == 0 )
      break;
    if ( v13 != -1073741191 )
      break;
    v5 = WcProcessWciReparsePointBounce(
           a1,
           *(struct _FLT_INSTANCE **)(a2 + 24),
           a3,
           a4,
           WORD5(v22[2]),
           &v17,
           v15,
           &v16,
           (struct _FILE_OBJECT **)&v20);
    if ( v5 < 0 )
      break;
    v7 = v15[0];
  }
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v20 )
    ObfDereferenceObject(v20);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001939c  push    rbp
0x14001939e  push    rbx
0x14001939f  push    rsi
0x1400193a0  push    rdi
0x1400193a1  push    r13
0x1400193a3  push    r14
0x1400193a5  push    r15
0x1400193a7  lea     rbp, [rsp-27h]
0x1400193ac  sub     rsp, 0C0h
0x1400193b3  mov     rax, cs:__security_cookie
0x1400193ba  xor     rax, rsp
0x1400193bd  mov     [rbp+57h+var_38], rax
0x1400193c1  mov     rax, [rcx+10h]
0x1400193c5  xor     ebx, ebx
0x1400193c7  xorps   xmm0, xmm0
0x1400193ca  mov     [rbp+57h+FileHandle], rbx
0x1400193ce  mov     r13, r9
0x1400193d1  mov     [rbp+57h+Object], rbx
0x1400193d5  xor     r9b, r9b
0x1400193d8  mov     [rbp+57h+var_9C], ebx
0x1400193db  mov     [rbp+57h+var_A0], r9b
0x1400193df  mov     r15d, r8d
0x1400193e2  movups  [rbp+57h+var_68], xmm0
0x1400193e6  mov     [rbp+57h+var_80], rbx
0x1400193ea  mov     r14, rdx
0x1400193ed  movups  [rbp+57h+var_58], xmm0
0x1400193f1  mov     [rbp+57h+var_98], ebx
0x1400193f4  mov     rsi, rcx
0x1400193f7  movups  [rbp+57h+var_48], xmm0
0x1400193fb  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x1400193ff  mov     edi, [rax+20h]
0x140019402  and     edi, 41h
0x140019405  or      edi, 28h
0x140019408  test    r9b, r9b
0x14001940b  jnz     loc_1400194E9
0x140019411  mov     rcx, [r14+18h]; Instance
0x140019415  lea     rax, [rbp+57h+var_78]
0x140019419  mov     qword ptr [rbp+57h+var_68], rax
0x14001941d  lea     rdx, [r13+8]
0x140019421  lea     rax, [rbp+57h+var_78]
0x140019425  mov     dword ptr [rbp+57h+var_58], r15d
0x140019429  mov     qword ptr [rbp+57h+var_68+8], rax
0x14001942d  xorps   xmm0, xmm0
0x140019430  lea     rax, [rbp+57h+var_68]
0x140019434  mov     dword ptr [rbp+57h+var_58+4], 80000004h
0x14001943b  mov     [rbp+57h+var_78], rax
0x14001943f  xor     r9d, r9d
0x140019442  lea     rax, [rbp+57h+var_68]
0x140019446  mov     dword ptr [rbp+57h+var_48+8], 30h ; '0'
0x14001944d  mov     [rbp+57h+var_78+8], rax
0x140019451  xor     r8d, r8d
0x140019454  lea     rax, [rbp+57h+Object]
0x140019458  mov     [rsp+0F0h+FileObject], rax; FileObject
0x14001945d  lea     rax, [rbp+57h+FileHandle]
0x140019461  mov     [rsp+0F0h+var_B0], rax; FileHandle
0x140019466  lea     rax, [rbp+57h+var_78]
0x14001946a  mov     [rsp+0F0h+var_B8], rax; __int64
0x14001946f  mov     [rsp+0F0h+var_C0], 7; ULONG
0x140019477  mov     [rsp+0F0h+var_C8], edi; ULONG
0x14001947b  mov     [rsp+0F0h+DesiredAccess], 80h; DesiredAccess
0x140019483  movups  [rbp+57h+var_58+8], xmm0
0x140019487  call    WcOpenReparsePoint
0x14001948c  test    byte ptr [rbp+57h+var_58+4], 1
0x140019490  mov     ebx, eax
0x140019492  jz      short loc_1400194E9
0x140019494  cmp     eax, 0C0000279h
0x140019499  jnz     short loc_1400194E9
0x14001949b  mov     rdx, [r14+18h]
0x14001949f  lea     rax, [rbp+57h+var_80]
0x1400194a3  mov     [rsp+0F0h+var_B0], rax
0x1400194a8  mov     r9, r13
0x1400194ab  lea     rax, [rbp+57h+var_9C]
0x1400194af  mov     r8d, r15d
0x1400194b2  mov     [rsp+0F0h+var_B8], rax
0x1400194b7  mov     rcx, rsi
0x1400194ba  lea     rax, [rbp+57h+var_A0]
0x1400194be  mov     qword ptr [rsp+0F0h+var_C0], rax
0x1400194c3  lea     rax, [rbp+57h+var_98]
0x1400194c7  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400194cc  movzx   eax, word ptr [rbp+57h+var_48+0Ah]
0x1400194d0  mov     word ptr [rsp+0F0h+DesiredAccess], ax
0x1400194d5  call    WcProcessWciReparsePointBounce
0x1400194da  mov     ebx, eax
0x1400194dc  test    eax, eax
0x1400194de  js      short loc_1400194E9
0x1400194e0  mov     r9b, [rbp+57h+var_A0]
0x1400194e4  jmp     loc_140019408
0x1400194e9  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400194ed  test    rcx, rcx
0x1400194f0  jz      short loc_1400194FE
0x1400194f2  call    cs:__imp_FltClose
0x1400194f9  nop     dword ptr [rax+rax+00h]
0x1400194fe  mov     rcx, [rbp+57h+Object]; Object
0x140019502  test    rcx, rcx
0x140019505  jz      short loc_140019513
0x140019507  call    cs:__imp_ObfDereferenceObject
0x14001950e  nop     dword ptr [rax+rax+00h]
0x140019513  mov     rcx, [rbp+57h+var_80]; Object
0x140019517  test    rcx, rcx
0x14001951a  jz      short loc_140019528
0x14001951c  call    cs:__imp_ObfDereferenceObject
0x140019523  nop     dword ptr [rax+rax+00h]
0x140019528  mov     eax, ebx
0x14001952a  mov     rcx, [rbp+57h+var_38]
0x14001952e  xor     rcx, rsp; StackCookie
0x140019531  call    __security_check_cookie
0x140019536  add     rsp, 0C0h
0x14001953d  pop     r15
0x14001953f  pop     r14
0x140019541  pop     r13
0x140019543  pop     rdi
0x140019544  pop     rsi
0x140019545  pop     rbx
0x140019546  pop     rbp
0x140019547  retn
```
