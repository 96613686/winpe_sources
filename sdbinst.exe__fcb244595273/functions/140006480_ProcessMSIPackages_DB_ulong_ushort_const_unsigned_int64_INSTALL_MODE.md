# ProcessMSIPackages(_DB *,ulong,ushort const *,unsigned __int64,_INSTALL_MODE)

- ea: `0x140006480`
- end: `0x140006604`
- name: `?ProcessMSIPackages@@YAHPEAU_DB@@KPEBG_KW4_INSTALL_MODE@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x140004df8`

## callees

- `0x140001e68`
- `0x140002206`
- `0x140005988`
- `0x140006238`
- `0x140006480`
- `0x1400075a8`
- `0x140013824`
- `0x140014380`
- `0x14001443c`
- `0x14002e420`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1400065a9`
- `ntdll!RtlFreeUnicodeString` at `0x1400065a9`
- `ntdll!RtlStringFromGUID` at `0x140006531`
- `ntdll!RtlStringFromGUID` at `0x140006531`

## pseudocode

```c
__int64 __fastcall ProcessMSIPackages(__int64 a1, __int64 a2, unsigned __int16 *a3, __int64 a4, int a5)
{
  unsigned int v7; // r12d
  unsigned int v9; // ebx
  unsigned int i; // esi
  unsigned int FirstTag; // eax
  GUID *BinaryTagData; // rax
  __int64 Length; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned int v17; // eax
  struct _UNICODE_STRING GuidString; // [rsp+20h] [rbp-A1h] BYREF
  GUID Guid; // [rsp+30h] [rbp-91h] BYREF
  WCHAR SubKey[64]; // [rsp+40h] [rbp-81h] BYREF

  Guid = 0;
  v7 = a2;
  GuidString = 0;
  v9 = 1;
  for ( i = SdbFindFirstTag(a1, a2, 28690); i; i = SdbFindNextTag(a1, v7, i) )
  {
    if ( !v9 )
      return v9;
    FirstTag = SdbFindFirstTag(a1, i, 36870);
    if ( FirstTag && (BinaryTagData = (GUID *)SdbGetBinaryTagData(a1, FirstTag)) != 0 )
    {
      Guid = *BinaryTagData;
      if ( RtlStringFromGUID(&Guid, &GuidString) < 0 )
      {
        PrintMessage(0x407u);
        return 0;
      }
      if ( (GuidString.Length & 0xFFFEu) > 0x7E )
      {
        PrintMessage(0x409u);
        return 0;
      }
      Length = GuidString.Length;
      memcpy_0(SubKey, GuidString.Buffer, GuidString.Length);
      v16 = Length & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v16 >= 0x80 )
        _report_rangecheckfailure(v15, v14);
      *(WCHAR *)((char *)SubKey + v16) = 0;
      if ( a5 )
        v17 = UninstallSdbEntry(SubKey, a3, 0);
      else
        v17 = InstallSdbEntry(SubKey, a3, a4, 0);
      v9 = v17;
      RtlFreeUnicodeString(&GuidString);
    }
    else if ( (unsigned int)(a5 - 1) > 1 )
    {
      PrintMessage(0x408u);
      return 0;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x140006480  push    rbp
0x140006482  push    rbx
0x140006483  push    rsi
0x140006484  push    rdi
0x140006485  push    r12
0x140006487  push    r13
0x140006489  push    r14
0x14000648b  push    r15
0x14000648d  lea     rbp, [rsp-17h]
0x140006492  sub     rsp, 0D8h
0x140006499  mov     rax, cs:__security_cookie
0x1400064a0  xor     rax, rsp
0x1400064a3  mov     [rbp+4Fh+var_50], rax
0x1400064a7  xorps   xmm0, xmm0
0x1400064aa  mov     r15, r8
0x1400064ad  mov     r8d, 7012h
0x1400064b3  mov     r13, r9
0x1400064b6  movups  xmmword ptr [rsp+110h+Guid.Data1], xmm0
0x1400064bb  mov     r12d, edx
0x1400064be  mov     r14, rcx
0x1400064c1  movups  xmmword ptr [rsp+110h+GuidString.Length], xmm0
0x1400064c6  mov     ebx, 1
0x1400064cb  call    SdbFindFirstTag
0x1400064d0  mov     esi, eax
0x1400064d2  test    eax, eax
0x1400064d4  jz      loc_1400065DC
0x1400064da  mov     edi, [rbp+4Fh+arg_20]
0x1400064dd  test    ebx, ebx
0x1400064df  jz      loc_1400065DC
0x1400064e5  mov     r8d, 9006h
0x1400064eb  mov     edx, esi
0x1400064ed  mov     rcx, r14
0x1400064f0  call    SdbFindFirstTag
0x1400064f5  test    eax, eax
0x1400064f7  jnz     short loc_14000650F
0x1400064f9  lea     eax, [rdi-1]
0x1400064fc  cmp     eax, 1
0x1400064ff  jbe     loc_1400065AF
0x140006505  mov     ecx, 408h
0x14000650a  jmp     loc_1400065D5
0x14000650f  mov     edx, eax
0x140006511  mov     rcx, r14
0x140006514  call    SdbGetBinaryTagData
0x140006519  test    rax, rax
0x14000651c  jz      short loc_1400064F9
0x14000651e  movups  xmm0, xmmword ptr [rax]
0x140006521  lea     rdx, [rsp+110h+GuidString]; GuidString
0x140006526  lea     rcx, [rsp+110h+Guid]; Guid
0x14000652b  movdqu  xmmword ptr [rsp+110h+Guid.Data1], xmm0
0x140006531  call    cs:__imp_RtlStringFromGUID
0x140006537  test    eax, eax
0x140006539  js      loc_1400065D0
0x14000653f  movzx   eax, [rsp+110h+GuidString.Length]
0x140006544  mov     ecx, 0FFFEh
0x140006549  and     ax, cx
0x14000654c  cmp     ax, 7Eh ; '~'
0x140006550  ja      short loc_1400065C9
0x140006552  movzx   ebx, [rsp+110h+GuidString.Length]
0x140006557  lea     rcx, [rsp+110h+SubKey]; void *
0x14000655c  mov     rdx, [rsp+110h+GuidString.Buffer]; Src
0x140006561  mov     r8d, ebx; Size
0x140006564  call    memcpy_0
0x140006569  and     rbx, 0FFFFFFFFFFFFFFFEh
0x14000656d  cmp     rbx, 80h
0x140006574  jnb     loc_1400065FE
0x14000657a  xor     eax, eax
0x14000657c  lea     rcx, [rsp+110h+SubKey]; lpSubKey
0x140006581  mov     [rsp+rbx+110h+SubKey], ax
0x140006586  mov     rdx, r15; unsigned __int16 *
0x140006589  test    edi, edi
0x14000658b  jnz     short loc_14000659A
0x14000658d  xor     r9d, r9d; int
0x140006590  mov     r8, r13; unsigned __int64
0x140006593  call    ?InstallSdbEntry@@YAHPEBG0_KH@Z; InstallSdbEntry(ushort const *,ushort const *,unsigned __int64,int)
0x140006598  jmp     short loc_1400065A2
0x14000659a  xor     r8d, r8d; int
0x14000659d  call    ?UninstallSdbEntry@@YAHPEBG0H@Z; UninstallSdbEntry(ushort const *,ushort const *,int)
0x1400065a2  lea     rcx, [rsp+110h+GuidString]; UnicodeString
0x1400065a7  mov     ebx, eax
0x1400065a9  call    cs:__imp_RtlFreeUnicodeString
0x1400065af  mov     r8d, esi
0x1400065b2  mov     edx, r12d
0x1400065b5  mov     rcx, r14
0x1400065b8  call    SdbFindNextTag
0x1400065bd  mov     esi, eax
0x1400065bf  test    eax, eax
0x1400065c1  jnz     loc_1400064DD
0x1400065c7  jmp     short loc_1400065DC
0x1400065c9  mov     ecx, 409h
0x1400065ce  jmp     short loc_1400065D5
0x1400065d0  mov     ecx, 407h; unsigned int
0x1400065d5  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400065da  xor     ebx, ebx
0x1400065dc  mov     eax, ebx
0x1400065de  mov     rcx, [rbp+4Fh+var_50]
0x1400065e2  xor     rcx, rsp; StackCookie
0x1400065e5  call    __security_check_cookie
0x1400065ea  add     rsp, 0D8h
0x1400065f1  pop     r15
0x1400065f3  pop     r14
0x1400065f5  pop     r13
0x1400065f7  pop     r12
0x1400065f9  pop     rdi
0x1400065fa  pop     rsi
0x1400065fb  pop     rbx
0x1400065fc  pop     rbp
0x1400065fd  retn
0x1400065fe  call    __report_rangecheckfailure
```
