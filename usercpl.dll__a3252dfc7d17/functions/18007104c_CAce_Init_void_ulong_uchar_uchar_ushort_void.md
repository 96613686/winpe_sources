# CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)

- ea: `0x18007104c`
- end: `0x1800711b9`
- name: `?_Init@CAce@@AEAAJPEAXKEEG0@Z`
- size: `365`
- prototype: `__int64 __fastcall(CAce *this, void *, int, char, unsigned __int8, unsigned __int16, void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800711c0`

## callees

- `0x18007104c`
- `0x180077272`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710d1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180071099`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007111d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180071099`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007111d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800710c7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800710c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800710ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071138`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800710ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071138`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800710f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800710f3`
- `ADVAPI32!IsValidSid` at `0x180071088`
- `ADVAPI32!IsValidSid` at `0x180071088`
- `ntdll!RtlMapGenericMask` at `0x180071176`
- `ntdll!RtlMapGenericMask` at `0x180071176`

## pseudocode

```c
__int64 __fastcall CAce::_Init(
        CAce *this,
        void *a2,
        int a3,
        char a4,
        unsigned __int8 a5,
        unsigned __int16 a6,
        void *Src)
{
  unsigned int v12; // esi
  DWORD LengthSid; // ebx
  HLOCAL v14; // rax
  void *v15; // r14
  signed int LastError; // eax
  unsigned int v17; // ebx
  DWORD v18; // edx
  HLOCAL v19; // rax
  bool v20; // zf
  unsigned int v21; // eax

  if ( !a2 )
    return 2147942487LL;
  *((_QWORD *)this + 1) = 0;
  v12 = -2147024809;
  if ( IsValidSid(a2) )
  {
    LengthSid = GetLengthSid(a2);
    v12 = -2147024882;
    v14 = LocalAlloc(0x40u, LengthSid);
    v15 = v14;
    if ( v14 )
    {
      if ( !CopySid(LengthSid, v14, a2) )
      {
        LastError = GetLastError();
        v17 = LastError;
        if ( LastError > 0 )
          v17 = (unsigned __int16)LastError | 0x80070000;
        if ( (v17 & 0x80000000) == 0 )
          v17 = -2147467259;
        LocalFree(v15);
        return v17;
      }
      v17 = 0;
      *((_QWORD *)this + 1) = v15;
      if ( !Src || (v18 = GetLengthSid(a2) + 8, a6 <= v18) )
      {
LABEL_15:
        *(_BYTE *)this = a5;
        *((_DWORD *)this + 1) = a3;
        *((_BYTE *)this + 1) = a4;
        *((_WORD *)this + 1) = a6;
        RtlMapGenericMask((PACCESS_MASK)this + 1, (PGENERIC_MAPPING)&GenericMapping);
        v20 = *(_BYTE *)this == 0;
        v21 = 0x80000000;
        *((_DWORD *)this + 7) = 0x80000000;
        if ( v20 || *(_BYTE *)this == 9 )
        {
          v21 = -2147483647;
          *((_DWORD *)this + 7) = -2147483647;
        }
        if ( (*((_BYTE *)this + 1) & 0x10) != 0 )
          *((_DWORD *)this + 7) = v21 | 0x20;
        return v17;
      }
      *((_DWORD *)this + 6) = a6 - v18;
      v19 = LocalAlloc(0x40u, a6 - v18);
      *((_QWORD *)this + 2) = v19;
      if ( v19 )
      {
        memcpy_0(v19, Src, *((unsigned int *)this + 6));
        goto LABEL_15;
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18007104c  push    rbx
0x18007104e  push    rbp
0x18007104f  push    rsi
0x180071050  push    rdi
0x180071051  push    r12
0x180071053  push    r13
0x180071055  push    r14
0x180071057  push    r15
0x180071059  sub     rsp, 28h
0x18007105d  mov     r12b, r9b
0x180071060  mov     r13d, r8d
0x180071063  mov     rbp, rdx
0x180071066  mov     rdi, rcx
0x180071069  test    rdx, rdx
0x18007106c  jnz     short loc_180071078
0x18007106e  mov     eax, 80070057h
0x180071073  jmp     loc_1800711A8
0x180071078  mov     qword ptr [rcx+8], 0
0x180071080  mov     esi, 80070057h
0x180071085  mov     rcx, rbp; pSid
0x180071088  call    cs:__imp_IsValidSid
0x18007108e  test    eax, eax
0x180071090  jz      loc_1800711A4
0x180071096  mov     rcx, rbp; pSid
0x180071099  call    cs:__imp_GetLengthSid
0x18007109f  mov     edx, eax; uBytes
0x1800710a1  mov     ecx, 40h ; '@'; uFlags
0x1800710a6  mov     ebx, eax
0x1800710a8  mov     esi, 8007000Eh
0x1800710ad  call    cs:__imp_LocalAlloc
0x1800710b3  mov     r14, rax
0x1800710b6  test    rax, rax
0x1800710b9  jz      loc_1800711A4
0x1800710bf  mov     r8, rbp; pSourceSid
0x1800710c2  mov     rdx, rax; pDestinationSid
0x1800710c5  mov     ecx, ebx; nDestinationSidLength
0x1800710c7  call    cs:__imp_CopySid
0x1800710cd  test    eax, eax
0x1800710cf  jnz     short loc_1800710FE
0x1800710d1  call    cs:__imp_GetLastError
0x1800710d7  mov     ebx, eax
0x1800710d9  test    eax, eax
0x1800710db  jle     short loc_1800710E6
0x1800710dd  movzx   ebx, ax
0x1800710e0  or      ebx, 80070000h
0x1800710e6  test    ebx, ebx
0x1800710e8  mov     eax, 80004005h
0x1800710ed  mov     rcx, r14; hMem
0x1800710f0  cmovns  ebx, eax
0x1800710f3  call    cs:__imp_LocalFree
0x1800710f9  jmp     loc_1800711A6
0x1800710fe  movzx   r15d, [rsp+68h+arg_28]
0x180071107  xor     ebx, ebx
0x180071109  mov     [rdi+8], r14
0x18007110d  mov     r14, [rsp+68h+Src]
0x180071115  test    r14, r14
0x180071118  jz      short loc_180071156
0x18007111a  mov     rcx, rbp; pSid
0x18007111d  call    cs:__imp_GetLengthSid
0x180071123  lea     edx, [rax+8]
0x180071126  mov     eax, r15d
0x180071129  cmp     r15d, edx
0x18007112c  jbe     short loc_180071156
0x18007112e  sub     eax, edx
0x180071130  lea     ecx, [rbx+40h]; uFlags
0x180071133  mov     edx, eax; uBytes
0x180071135  mov     [rdi+18h], edx
0x180071138  call    cs:__imp_LocalAlloc
0x18007113e  mov     [rdi+10h], rax
0x180071142  test    rax, rax
0x180071145  jz      short loc_1800711A4
0x180071147  mov     r8d, [rdi+18h]; Size
0x18007114b  mov     rdx, r14; Src
0x18007114e  mov     rcx, rax; void *
0x180071151  call    memcpy_0
0x180071156  mov     al, [rsp+68h+arg_20]
0x18007115d  lea     rcx, [rdi+4]; AccessMask
0x180071161  lea     rdx, GenericMapping; GenericMapping
0x180071168  mov     [rdi], al
0x18007116a  mov     [rcx], r13d
0x18007116d  mov     [rdi+1], r12b
0x180071171  mov     [rdi+2], r15w
0x180071176  call    cs:__imp_RtlMapGenericMask
0x18007117c  cmp     byte ptr [rdi], 0
0x18007117f  mov     eax, 80000000h
0x180071184  mov     [rdi+1Ch], eax
0x180071187  jz      short loc_18007118E
0x180071189  cmp     byte ptr [rdi], 9
0x18007118c  jnz     short loc_180071196
0x18007118e  mov     eax, 80000001h
0x180071193  mov     [rdi+1Ch], eax
0x180071196  test    byte ptr [rdi+1], 10h
0x18007119a  jz      short loc_1800711A6
0x18007119c  or      eax, 20h
0x18007119f  mov     [rdi+1Ch], eax
0x1800711a2  jmp     short loc_1800711A6
0x1800711a4  mov     ebx, esi
0x1800711a6  mov     eax, ebx
0x1800711a8  add     rsp, 28h
0x1800711ac  pop     r15
0x1800711ae  pop     r14
0x1800711b0  pop     r13
0x1800711b2  pop     r12
0x1800711b4  pop     rdi
0x1800711b5  pop     rsi
0x1800711b6  pop     rbp
0x1800711b7  pop     rbx
0x1800711b8  retn
```
