# CreateKeyRecursively

- ea: `0x1400096a0`
- end: `0x14000991c`
- name: `CreateKeyRecursively`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400094c0`

## callees

- `0x1400096a0`

## import_xrefs

- `ntdll!NtClose` at `0x140009891`
- `ntdll!NtClose` at `0x1400098ed`
- `ntdll!NtClose` at `0x140009891`
- `ntdll!NtClose` at `0x1400098ed`
- `ntdll!NtCreateKey` at `0x140009745`
- `ntdll!NtCreateKey` at `0x1400097e2`
- `ntdll!NtCreateKey` at `0x140009885`
- `ntdll!NtCreateKey` at `0x1400098e1`
- `ntdll!NtCreateKey` at `0x140009745`
- `ntdll!NtCreateKey` at `0x1400097e2`
- `ntdll!NtCreateKey` at `0x140009885`
- `ntdll!NtCreateKey` at `0x1400098e1`

## pseudocode

```c
__int64 __fastcall CreateKeyRecursively(void **a1, void *a2, __int128 *a3, char a4)
{
  __int128 v4; // xmm0
  ULONG CreateOptions; // r12d
  int v7; // r14d
  ULONG v8; // r15d
  NTSTATUS v9; // edi
  __int64 result; // rax
  unsigned __int16 v11; // bx
  _WORD *v12; // rsi
  __int16 v13; // di
  _WORD *v14; // rsi
  __int16 v15; // ax
  NTSTATUS v16; // ebx
  __int128 v17; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+C8h] [rbp+48h] BYREF
  ULONG Disposition; // [rsp+D8h] [rbp+58h] BYREF

  KeyHandle = a2;
  v4 = *a3;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  Disposition = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  CreateOptions = a4 != 0 ? 3 : 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v17;
  v7 = a4 != 0 ? 0x20 : 0;
  v17 = v4;
  v8 = a4 != 0 ? 320 : 64;
  ObjectAttributes.Attributes = v8;
  v9 = NtCreateKey(&KeyHandle, v7 + 131078, &ObjectAttributes, 0, 0, CreateOptions, &Disposition);
  result = 3221225524LL;
  if ( v9 != -1073741772 )
  {
LABEL_24:
    if ( v9 >= 0 )
      *a1 = KeyHandle;
    return (unsigned int)v9;
  }
  WORD1(v17) = v17;
  v11 = (unsigned __int16)v17 >> 1;
  ObjectAttributes.Attributes = 64;
  v12 = (_WORD *)(*((_QWORD *)&v17 + 1) - 2LL + 2LL * ((unsigned __int16)v17 >> 1));
  while ( v9 == -1073741772 )
  {
    if ( !v11 )
      return result;
    while ( *v12 != 92 )
    {
      --v12;
      if ( !--v11 )
        goto LABEL_10;
    }
    do
    {
      --v12;
      --v11;
    }
    while ( v11 && *v12 == 92 );
LABEL_10:
    LOWORD(v17) = 2 * v11;
    v9 = NtCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, &Disposition);
    result = 3221225524LL;
  }
  if ( v9 >= 0 )
  {
    ObjectAttributes.RootDirectory = KeyHandle;
    v13 = (WORD1(v17) >> 1) - v11;
    v14 = (_WORD *)(*((_QWORD *)&v17 + 1) + 2LL * v11);
    while ( 1 )
    {
      KeyHandle = 0;
      if ( !v13 )
        break;
      do
      {
        if ( *v14 != 92 )
          break;
        ++v14;
        --v13;
      }
      while ( v13 );
      *((_QWORD *)&v17 + 1) = v14;
      v15 = 0;
      for ( LOWORD(v17) = 0; v13; --v13 )
      {
        if ( *v14 == 92 )
          break;
        v15 += 2;
        ++v14;
        LOWORD(v17) = v15;
      }
      WORD1(v17) = v15;
      if ( !v13 )
        break;
      v16 = NtCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, &Disposition);
      NtClose(ObjectAttributes.RootDirectory);
      if ( v16 < 0 )
        return (unsigned int)v16;
      ObjectAttributes.RootDirectory = KeyHandle;
    }
    ObjectAttributes.Attributes = v8;
    v9 = NtCreateKey(&KeyHandle, v7 + 131078, &ObjectAttributes, 0, 0, CreateOptions, &Disposition);
    NtClose(ObjectAttributes.RootDirectory);
    goto LABEL_24;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400096a0  mov     [rsp-38h+arg_0], rbx
0x1400096a5  mov     [rsp-38h+KeyHandle], rdx
0x1400096aa  push    rbp
0x1400096ab  push    rsi
0x1400096ac  push    rdi
0x1400096ad  push    r12
0x1400096af  push    r13
0x1400096b1  push    r14
0x1400096b3  push    r15
0x1400096b5  mov     rbp, rsp
0x1400096b8  sub     rsp, 80h
0x1400096bf  movups  xmm0, xmmword ptr [r8]
0x1400096c3  xor     ebx, ebx
0x1400096c5  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400096cd  mov     al, r9b
0x1400096d0  mov     [rbp+arg_18], ebx
0x1400096d3  neg     al
0x1400096d5  mov     dword ptr [rbp+ObjectAttributes+1Ch], ebx
0x1400096d8  mov     al, r9b
0x1400096db  mov     [rbp+KeyHandle], rbx
0x1400096df  sbb     r12d, r12d
0x1400096e2  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x1400096e6  and     r12d, 3
0x1400096ea  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400096ee  neg     al
0x1400096f0  mov     r13, rcx
0x1400096f3  lea     rax, [rbp+var_40]
0x1400096f7  sbb     r14d, r14d
0x1400096fa  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400096fe  and     r14d, 20h
0x140009702  lea     rax, [rbp+arg_18]
0x140009706  neg     r9b
0x140009709  mov     [rsp+80h+Disposition], rax; Disposition
0x14000970e  movdqu  [rbp+var_40], xmm0
0x140009713  sbb     r15d, r15d
0x140009716  mov     [rsp+80h+CreateOptions], r12d; CreateOptions
0x14000971b  xorps   xmm0, xmm0
0x14000971e  mov     [rsp+80h+Class], rbx; Class
0x140009723  and     r15d, 100h
0x14000972a  lea     edx, [r14+20006h]; DesiredAccess
0x140009731  add     r15d, 40h ; '@'
0x140009735  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140009739  xor     r9d, r9d; TitleIndex
0x14000973c  mov     [rbp+ObjectAttributes.Attributes], r15d
0x140009740  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140009745  call    cs:__imp_NtCreateKey
0x14000974b  mov     edi, eax
0x14000974d  mov     eax, 0C0000034h
0x140009752  cmp     edi, eax
0x140009754  jnz     loc_1400098F3
0x14000975a  movzx   ebx, word ptr [rbp+var_40]
0x14000975e  mov     rcx, qword ptr [rbp+var_40+8]
0x140009762  mov     word ptr [rbp+var_40+2], bx
0x140009766  shr     bx, 1
0x140009769  movzx   esi, bx
0x14000976c  sub     rcx, 2
0x140009770  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140009777  lea     rsi, [rcx+rsi*2]
0x14000977b  mov     r9d, 0FFFFh
0x140009781  mov     r8d, 2
0x140009787  cmp     edi, eax
0x140009789  jnz     short loc_1400097F1
0x14000978b  xor     ecx, ecx
0x14000978d  test    bx, bx
0x140009790  jz      loc_140009901
0x140009796  cmp     word ptr [rsi], 5Ch ; '\'
0x14000979a  jz      short loc_1400097AD
0x14000979c  sub     rsi, r8
0x14000979f  add     bx, r9w
0x1400097a3  jnz     short loc_140009796
0x1400097a5  jmp     short loc_1400097B6
0x1400097a7  cmp     word ptr [rsi], 5Ch ; '\'
0x1400097ab  jnz     short loc_1400097B6
0x1400097ad  sub     rsi, r8
0x1400097b0  add     bx, r9w
0x1400097b4  jnz     short loc_1400097A7
0x1400097b6  movzx   eax, bx
0x1400097b9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400097bd  add     ax, ax
0x1400097c0  xor     r9d, r9d; TitleIndex
0x1400097c3  mov     word ptr [rbp+var_40], ax
0x1400097c7  mov     edx, 20006h; DesiredAccess
0x1400097cc  lea     rax, [rbp+arg_18]
0x1400097d0  mov     [rsp+80h+Disposition], rax; Disposition
0x1400097d5  mov     [rsp+80h+CreateOptions], ecx; CreateOptions
0x1400097d9  mov     [rsp+80h+Class], rcx; Class
0x1400097de  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400097e2  call    cs:__imp_NtCreateKey
0x1400097e8  mov     edi, eax
0x1400097ea  mov     eax, 0C0000034h
0x1400097ef  jmp     short loc_14000977B
0x1400097f1  xor     edx, edx
0x1400097f3  test    edi, edi
0x1400097f5  js      loc_1400098FF
0x1400097fb  mov     rax, [rbp+KeyHandle]
0x1400097ff  movzx   edi, word ptr [rbp+var_40+2]
0x140009803  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140009807  mov     rax, qword ptr [rbp+var_40+8]
0x14000980b  movzx   ecx, bx
0x14000980e  shr     di, 1
0x140009811  sub     di, bx
0x140009814  lea     rsi, [rax+rcx*2]
0x140009818  mov     [rbp+KeyHandle], rdx
0x14000981c  test    di, di
0x14000981f  jz      loc_1400098B8
0x140009825  cmp     word ptr [rsi], 5Ch ; '\'
0x140009829  jnz     short loc_140009834
0x14000982b  add     rsi, r8
0x14000982e  add     di, r9w
0x140009832  jnz     short loc_140009825
0x140009834  mov     qword ptr [rbp+var_40+8], rsi
0x140009838  mov     eax, edx
0x14000983a  mov     word ptr [rbp+var_40], dx
0x14000983e  test    di, di
0x140009841  jz      short loc_14000985A
0x140009843  cmp     word ptr [rsi], 5Ch ; '\'
0x140009847  jz      short loc_14000985A
0x140009849  add     ax, r8w
0x14000984d  add     rsi, r8
0x140009850  mov     word ptr [rbp+var_40], ax
0x140009854  add     di, r9w
0x140009858  jnz     short loc_140009843
0x14000985a  mov     word ptr [rbp+var_40+2], ax
0x14000985e  test    di, di
0x140009861  jz      short loc_1400098B8
0x140009863  lea     rax, [rbp+arg_18]
0x140009867  xor     r9d, r9d; TitleIndex
0x14000986a  mov     [rsp+80h+Disposition], rax; Disposition
0x14000986f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140009873  mov     [rsp+80h+CreateOptions], edx; CreateOptions
0x140009877  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000987b  mov     [rsp+80h+Class], rdx; Class
0x140009880  mov     edx, 20006h; DesiredAccess
0x140009885  call    cs:__imp_NtCreateKey
0x14000988b  mov     rcx, [rbp+ObjectAttributes.RootDirectory]; Handle
0x14000988f  mov     ebx, eax
0x140009891  call    cs:__imp_NtClose
0x140009897  xor     edx, edx
0x140009899  test    ebx, ebx
0x14000989b  js      short loc_1400098B4
0x14000989d  mov     rax, [rbp+KeyHandle]
0x1400098a1  lea     r8d, [rdx+2]
0x1400098a5  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400098a9  mov     r9d, 0FFFFh
0x1400098af  jmp     loc_140009818
0x1400098b4  mov     eax, ebx
0x1400098b6  jmp     short loc_140009901
0x1400098b8  lea     rax, [rbp+arg_18]
0x1400098bc  mov     [rbp+ObjectAttributes.Attributes], r15d
0x1400098c0  mov     [rsp+80h+Disposition], rax; Disposition
0x1400098c5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400098c9  mov     [rsp+80h+CreateOptions], r12d; CreateOptions
0x1400098ce  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400098d2  mov     [rsp+80h+Class], rdx; Class
0x1400098d7  xor     r9d, r9d; TitleIndex
0x1400098da  lea     edx, [r14+20006h]; DesiredAccess
0x1400098e1  call    cs:__imp_NtCreateKey
0x1400098e7  mov     rcx, [rbp+ObjectAttributes.RootDirectory]; Handle
0x1400098eb  mov     edi, eax
0x1400098ed  call    cs:__imp_NtClose
0x1400098f3  test    edi, edi
0x1400098f5  js      short loc_1400098FF
0x1400098f7  mov     rax, [rbp+KeyHandle]
0x1400098fb  mov     [r13+0], rax
0x1400098ff  mov     eax, edi
0x140009901  mov     rbx, [rsp+80h+arg_0]
0x140009909  add     rsp, 80h
0x140009910  pop     r15
0x140009912  pop     r14
0x140009914  pop     r13
0x140009916  pop     r12
0x140009918  pop     rdi
0x140009919  pop     rsi
0x14000991a  pop     rbp
0x14000991b  retn
```
