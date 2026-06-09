# CSection::OpenSection(ushort const *,bool)

- ea: `0x180005850`
- end: `0x180005991`
- name: `?OpenSection@CSection@@IEAAJPEBG_N@Z`
- size: `321`
- prototype: `int __fastcall(CSection *this, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000546c`

## callees

- `0x180005850`
- `0x180006a08`
- `0x18000f300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005932`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180005902`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180005902`
- `ntdll!NtOpenSection` at `0x1800058d2`
- `ntdll!NtOpenSection` at `0x1800058d2`
- `ntdll!RtlInitUnicodeString` at `0x180005892`
- `ntdll!RtlInitUnicodeString` at `0x180005892`

## pseudocode

```c
int __fastcall CSection::OpenSection(CSection *this, const unsigned __int16 *a2, char a3)
{
  int v3; // edi
  ACCESS_MASK v7; // edx
  NTSTATUS v8; // eax
  LPVOID v9; // rax
  int result; // eax
  signed int LastError; // eax
  unsigned int v12; // edx
  int v13; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-68h] BYREF

  v3 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( !*((_QWORD *)this + 66) )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    v7 = *((_DWORD *)this + 137);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Attributes = 64;
    v8 = NtOpenSection((PHANDLE)this + 66, v7, &ObjectAttributes);
    if ( v8 < 0 )
    {
      v3 = v8 | 0x10000000;
      v12 = 53;
      goto LABEL_13;
    }
  }
  if ( a3 )
  {
    if ( !*((_QWORD *)this + 67) )
    {
      v9 = MapViewOfFile(*((HANDLE *)this + 66), *((_DWORD *)this + 138), 0, 0, 0);
      *((_QWORD *)this + 67) = v9;
      if ( !v9 )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 < 0 )
        {
          v12 = 65;
LABEL_13:
          RecordError(v3, v12);
          return v3;
        }
      }
    }
  }
  if ( *((_WORD *)this + 4) )
    return v3;
  result = StringCchCopyW((unsigned __int16 *)this + 4, 0x104u, a2);
  v13 = result;
  if ( result < 0 )
  {
    RecordError(result, 0x49u);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180005850  push    rbx
0x180005852  push    rbp
0x180005853  push    rsi
0x180005854  push    rdi
0x180005855  push    r14
0x180005857  push    r15
0x180005859  sub     rsp, 78h
0x18000585d  xorps   xmm0, xmm0
0x180005860  xor     r15d, r15d
0x180005863  mov     edi, r15d
0x180005866  movzx   ebp, r8b
0x18000586a  mov     r14, rdx
0x18000586d  mov     rbx, rcx
0x180005870  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x180005875  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x18000587a  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000587f  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x180005884  cmp     [rcx+210h], rdi
0x18000588b  jnz     short loc_1800058DC
0x18000588d  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x180005892  call    cs:__imp_RtlInitUnicodeString
0x180005898  mov     edx, [rbx+224h]; DesiredAccess
0x18000589e  lea     rax, [rsp+0A8h+DestinationString]
0x1800058a3  xorps   xmm0, xmm0
0x1800058a6  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x1800058ab  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1800058b0  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1800058b8  lea     rcx, [rbx+210h]; SectionHandle
0x1800058bf  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r15
0x1800058c4  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800058ca  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800058d2  call    cs:__imp_NtOpenSection
0x1800058d8  test    eax, eax
0x1800058da  js      short loc_180005959
0x1800058dc  test    bpl, bpl
0x1800058df  jz      short loc_180005914
0x1800058e1  cmp     [rbx+218h], r15
0x1800058e8  jnz     short loc_180005914
0x1800058ea  mov     edx, [rbx+228h]; dwDesiredAccess
0x1800058f0  xor     r9d, r9d; dwFileOffsetLow
0x1800058f3  mov     rcx, [rbx+210h]; hFileMappingObject
0x1800058fa  xor     r8d, r8d; dwFileOffsetHigh
0x1800058fd  mov     [rsp+0A8h+dwNumberOfBytesToMap], r15; dwNumberOfBytesToMap
0x180005902  call    cs:__imp_MapViewOfFile
0x180005908  mov     [rbx+218h], rax
0x18000590f  test    rax, rax
0x180005912  jz      short loc_180005932
0x180005914  test    edi, edi
0x180005916  js      short loc_180005923
0x180005918  cmp     r15w, [rbx+8]
0x18000591d  lea     rcx, [rbx+8]; unsigned __int16 *
0x180005921  jz      short loc_18000596E
0x180005923  mov     eax, edi
0x180005925  add     rsp, 78h
0x180005929  pop     r15
0x18000592b  pop     r14
0x18000592d  pop     rdi
0x18000592e  pop     rsi
0x18000592f  pop     rbp
0x180005930  pop     rbx
0x180005931  retn
0x180005932  call    cs:__imp_GetLastError
0x180005938  mov     edi, eax
0x18000593a  test    eax, eax
0x18000593c  jle     short loc_180005947
0x18000593e  movzx   edi, ax
0x180005941  or      edi, 80070000h
0x180005947  test    edi, edi
0x180005949  jns     short loc_180005918
0x18000594b  mov     edx, 41h ; 'A'; unsigned int
0x180005950  mov     ecx, edi; int
0x180005952  call    ?RecordError@@YAXJI@Z; RecordError(long,uint)
0x180005957  jmp     short loc_180005923
0x180005959  mov     edi, eax
0x18000595b  or      edi, 10000000h
0x180005961  jge     loc_1800058DC
0x180005967  mov     edx, 35h ; '5'
0x18000596c  jmp     short loc_180005950
0x18000596e  mov     r8, r14; unsigned __int16 *
0x180005971  mov     edx, 104h; unsigned __int64
0x180005976  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000597b  mov     ebx, eax
0x18000597d  test    eax, eax
0x18000597f  jns     short loc_180005925
0x180005981  mov     edx, 49h ; 'I'; unsigned int
0x180005986  mov     ecx, eax; int
0x180005988  call    ?RecordError@@YAXJI@Z; RecordError(long,uint)
0x18000598d  mov     eax, ebx
0x18000598f  jmp     short loc_180005925
```
