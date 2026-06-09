# SP_ENCLOSURE::Remove(void)

- ea: `0x14008db04`
- end: `0x14008dd47`
- name: `?Remove@SP_ENCLOSURE@@QEAAXXZ`
- size: `579`
- prototype: `void __fastcall(SP_ENCLOSURE *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x1400918a4`

## callees

- `0x140019500`
- `0x140068110`
- `0x140068600`
- `0x14008db04`
- `0x14008dd50`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14008dd12`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14008dd12`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008dbea`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008dc43`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008dbea`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008dc43`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14008dbfb`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14008dc54`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14008dbfb`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14008dc54`
- `ntoskrnl!RtlStringFromGUID` at `0x14008dc10`
- `ntoskrnl!RtlStringFromGUID` at `0x14008dc10`

## pseudocode

```c
void __fastcall SP_ENCLOSURE::Remove(SP_ENCLOSURE ***this)
{
  GUID **v2; // rcx
  GUID *v3; // rax
  GUID *v4; // rdx
  SP_ENCLOSURE **v5; // rcx
  SP_ENCLOSURE **v6; // rax
  char *v7; // rdx
  SP_ENCLOSURE **v8; // rcx
  SP_ENCLOSURE *v9; // rax
  SP_ENCLOSURE *v10; // r8
  char **v11; // r9
  __int64 v12; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[128]; // [rsp+40h] [rbp-C0h] BYREF

  GuidString = 0;
  memset(pszDest, 0, sizeof(pszDest));
  v2 = (GUID **)(this + 31);
  DestinationString = 0;
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (GUID *)v2 )
      break;
    if ( *(GUID ***)v3->Data4 != v2 )
      goto LABEL_23;
    v4 = *(GUID **)&v3->Data1;
    if ( *(GUID **)(*(_QWORD *)&v3->Data1 + 8LL) != v3 )
      goto LABEL_23;
    *v2 = v4;
    *(_QWORD *)v4->Data4 = v2;
    *(_QWORD *)v3->Data4 = v3;
    *(_QWORD *)&v3->Data1 = v3;
    *(_QWORD *)v3[3].Data4 = 0;
    *(_DWORD *)&v3[-20].Data4[4] = -1;
    v3[-33] = GUID_NULL;
  }
  v5 = *this;
  if ( (*this)[1] != (SP_ENCLOSURE *)this )
    goto LABEL_23;
  v6 = this[1];
  if ( *v6 != (SP_ENCLOSURE *)this )
    goto LABEL_23;
  *v6 = (SP_ENCLOSURE *)v5;
  v5[1] = (SP_ENCLOSURE *)v6;
  RtlStringCbPrintfW(
    pszDest,
    0x100u,
    L"\\DosDevices\\StorageEnclosure%d",
    *((unsigned int *)this + 26),
    *(_QWORD *)&DestinationString.Length,
    DestinationString.Buffer,
    *(_QWORD *)&GuidString.Length);
  RtlInitUnicodeString(&DestinationString, pszDest);
  IoDeleteSymbolicLink(&DestinationString);
  if ( RtlStringFromGUID((const GUID *const)this + 1, &GuidString) >= 0 )
  {
    RtlStringCbPrintfW(pszDest, 0x100u, L"\\DosDevices\\StorageEnclosure#%wZ", &GuidString);
    RtlInitUnicodeString(&DestinationString, pszDest);
    IoDeleteSymbolicLink(&DestinationString);
  }
  v7 = (char *)(this + 29);
  v8 = this[29];
  if ( v8 != (SP_ENCLOSURE **)(this + 29) )
  {
    if ( v8[1] == (SP_ENCLOSURE *)v7 )
    {
      v9 = *v8;
      if ( *((SP_ENCLOSURE ***)*v8 + 1) == v8 )
      {
        *(_QWORD *)v7 = v9;
        v10 = (SP_ENCLOSURE *)(v8 + 29);
        *((_QWORD *)v9 + 1) = v7;
        if ( *((SP_ENCLOSURE ***)v8[29] + 1) == v8 + 29 )
        {
          v11 = (char **)v8[30];
          if ( *v11 == (char *)v10 && *(char **)(*(_QWORD *)v7 + 8LL) == v7 && *this[30] == (SP_ENCLOSURE *)v7 )
          {
            *v11 = v7;
            v8[30] = (SP_ENCLOSURE *)this[30];
            *this[30] = v10;
            this[30] = (SP_ENCLOSURE **)v11;
            v12 = *(_QWORD *)v7;
            if ( *(char **)(*(_QWORD *)v7 + 8LL) == v7 && *v11 == v7 )
            {
              *v11 = (char *)v12;
              *(_QWORD *)(v12 + 8) = v11;
              this[30] = (SP_ENCLOSURE **)(this + 29);
              *(_QWORD *)v7 = v7;
              *((_DWORD *)v8 + 26) = *((_DWORD *)this + 26);
              SP_ENCLOSURE::Start((SP_ENCLOSURE *)v8);
              goto LABEL_20;
            }
          }
        }
      }
    }
LABEL_23:
    __fastfail(3u);
  }
LABEL_20:
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
}

```

## disassembly

```asm
0x14008db04  mov     [rsp-8+arg_8], rbx
0x14008db09  mov     [rsp-8+arg_10], rdi
0x14008db0e  push    rbp
0x14008db0f  lea     rbp, [rsp-50h]
0x14008db14  sub     rsp, 150h
0x14008db1b  mov     rax, cs:__security_cookie
0x14008db22  xor     rax, rsp
0x14008db25  mov     [rbp+50h+var_10], rax
0x14008db29  mov     rbx, rcx
0x14008db2c  xorps   xmm0, xmm0
0x14008db2f  mov     edi, 100h
0x14008db34  lea     rcx, [rsp+150h+pszDest]; void *
0x14008db39  mov     r8d, edi; Size
0x14008db3c  xor     edx, edx; Val
0x14008db3e  movups  xmmword ptr [rsp+150h+GuidString.Length], xmm0
0x14008db43  call    memset
0x14008db48  xorps   xmm0, xmm0
0x14008db4b  lea     rcx, [rbx+0F8h]
0x14008db52  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x14008db57  mov     rax, [rcx]
0x14008db5a  cmp     rax, rcx
0x14008db5d  jz      short loc_14008DBA7
0x14008db5f  cmp     [rax+8], rcx
0x14008db63  jnz     loc_14008DD40
0x14008db69  mov     rdx, [rax]
0x14008db6c  cmp     [rdx+8], rax
0x14008db70  jnz     loc_14008DD40
0x14008db76  mov     [rcx], rdx
0x14008db79  mov     [rdx+8], rcx
0x14008db7d  mov     [rax+8], rax
0x14008db81  mov     [rax], rax
0x14008db84  mov     qword ptr [rax+38h], 0
0x14008db8c  mov     dword ptr [rax-134h], 0FFFFFFFFh
0x14008db96  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14008db9d  movdqu  xmmword ptr [rax-210h], xmm0
0x14008dba5  jmp     short loc_14008DB57
0x14008dba7  mov     rcx, [rbx]
0x14008dbaa  cmp     [rcx+8], rbx
0x14008dbae  jnz     loc_14008DD40
0x14008dbb4  mov     rax, [rbx+8]
0x14008dbb8  cmp     [rax], rbx
0x14008dbbb  jnz     loc_14008DD40
0x14008dbc1  mov     [rax], rcx
0x14008dbc4  lea     r8, aDosdevicesStor; "\\DosDevices\\StorageEnclosure%d"
0x14008dbcb  mov     [rcx+8], rax
0x14008dbcf  mov     rdx, rdi; cbDest
0x14008dbd2  mov     r9d, [rbx+68h]
0x14008dbd6  lea     rcx, [rsp+150h+pszDest]; pszDest
0x14008dbdb  call    RtlStringCbPrintfW
0x14008dbe0  lea     rdx, [rsp+150h+pszDest]; SourceString
0x14008dbe5  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x14008dbea  call    cs:__imp_RtlInitUnicodeString
0x14008dbf1  nop     dword ptr [rax+rax+00h]
0x14008dbf6  lea     rcx, [rsp+150h+DestinationString]; SymbolicLinkName
0x14008dbfb  call    cs:__imp_IoDeleteSymbolicLink
0x14008dc02  nop     dword ptr [rax+rax+00h]
0x14008dc07  lea     rcx, [rbx+10h]; Guid
0x14008dc0b  lea     rdx, [rsp+150h+GuidString]; GuidString
0x14008dc10  call    cs:__imp_RtlStringFromGUID
0x14008dc17  nop     dword ptr [rax+rax+00h]
0x14008dc1c  test    eax, eax
0x14008dc1e  js      short loc_14008DC60
0x14008dc20  lea     r9, [rsp+150h+GuidString]
0x14008dc25  mov     rdx, rdi; cbDest
0x14008dc28  lea     r8, aDosdevicesStor_0; "\\DosDevices\\StorageEnclosure#%wZ"
0x14008dc2f  lea     rcx, [rsp+150h+pszDest]; pszDest
0x14008dc34  call    RtlStringCbPrintfW
0x14008dc39  lea     rdx, [rsp+150h+pszDest]; SourceString
0x14008dc3e  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x14008dc43  call    cs:__imp_RtlInitUnicodeString
0x14008dc4a  nop     dword ptr [rax+rax+00h]
0x14008dc4f  lea     rcx, [rsp+150h+DestinationString]; SymbolicLinkName
0x14008dc54  call    cs:__imp_IoDeleteSymbolicLink
0x14008dc5b  nop     dword ptr [rax+rax+00h]
0x14008dc60  lea     rdx, [rbx+0E8h]
0x14008dc67  mov     rcx, [rdx]; this
0x14008dc6a  cmp     rcx, rdx
0x14008dc6d  jz      loc_14008DD05
0x14008dc73  cmp     [rcx+8], rdx
0x14008dc77  jnz     loc_14008DD40
0x14008dc7d  mov     rax, [rcx]
0x14008dc80  cmp     [rax+8], rcx
0x14008dc84  jnz     loc_14008DD40
0x14008dc8a  mov     [rdx], rax
0x14008dc8d  lea     r8, [rcx+0E8h]
0x14008dc94  mov     [rax+8], rdx
0x14008dc98  mov     rax, [r8]
0x14008dc9b  cmp     [rax+8], r8
0x14008dc9f  jnz     loc_14008DD40
0x14008dca5  mov     r9, [r8+8]
0x14008dca9  cmp     [r9], r8
0x14008dcac  jnz     loc_14008DD40
0x14008dcb2  mov     rax, [rdx]
0x14008dcb5  cmp     [rax+8], rdx
0x14008dcb9  jnz     loc_14008DD40
0x14008dcbf  mov     rax, [rdx+8]
0x14008dcc3  cmp     [rax], rdx
0x14008dcc6  jnz     short loc_14008DD40
0x14008dcc8  mov     [r9], rdx
0x14008dccb  mov     rax, [rdx+8]
0x14008dccf  mov     [r8+8], rax
0x14008dcd3  mov     rax, [rdx+8]
0x14008dcd7  mov     [rax], r8
0x14008dcda  mov     [rdx+8], r9
0x14008dcde  mov     rax, [rdx]
0x14008dce1  cmp     [rax+8], rdx
0x14008dce5  jnz     short loc_14008DD40
0x14008dce7  cmp     [r9], rdx
0x14008dcea  jnz     short loc_14008DD40
0x14008dcec  mov     [r9], rax
0x14008dcef  mov     [rax+8], r9
0x14008dcf3  mov     [rdx+8], rdx
0x14008dcf7  mov     [rdx], rdx
0x14008dcfa  mov     eax, [rbx+68h]
0x14008dcfd  mov     [rcx+68h], eax
0x14008dd00  call    ?Start@SP_ENCLOSURE@@QEAAJXZ; SP_ENCLOSURE::Start(void)
0x14008dd05  cmp     [rsp+150h+GuidString.Buffer], 0
0x14008dd0b  jz      short loc_14008DD1E
0x14008dd0d  lea     rcx, [rsp+150h+GuidString]; UnicodeString
0x14008dd12  call    cs:__imp_RtlFreeUnicodeString
0x14008dd19  nop     dword ptr [rax+rax+00h]
0x14008dd1e  mov     rcx, [rbp+50h+var_10]
0x14008dd22  xor     rcx, rsp; StackCookie
0x14008dd25  call    __security_check_cookie
0x14008dd2a  lea     r11, [rsp+150h+var_s0]
0x14008dd32  mov     rbx, [r11+18h]
0x14008dd36  mov     rdi, [r11+20h]
0x14008dd3a  mov     rsp, r11
0x14008dd3d  pop     rbp
0x14008dd3e  retn
0x14008dd40  mov     ecx, 3
0x14008dd45  int     29h; Win8: RtlFailFast(ecx)
```
