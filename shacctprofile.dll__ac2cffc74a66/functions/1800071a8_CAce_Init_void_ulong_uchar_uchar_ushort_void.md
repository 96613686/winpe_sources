# CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)

- ea: `0x1800071a8`
- end: `0x180007315`
- name: `?_Init@CAce@@AEAAJPEAXKEEG0@Z`
- size: `365`
- prototype: `__int64 __fastcall(CAce *this, void *, int, char, unsigned __int8, unsigned __int16, void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006c70`
- `0x18000731c`

## callees

- `0x1800071a8`
- `0x180009730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000722d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000722d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800071e4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800071e4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800071f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007279`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800071f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007279`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007223`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007223`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000724f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000724f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007209`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007294`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007209`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007294`
- `ntdll!RtlMapGenericMask` at `0x1800072d2`
- `ntdll!RtlMapGenericMask` at `0x1800072d2`

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
0x1800071a8  push    rbx
0x1800071aa  push    rbp
0x1800071ab  push    rsi
0x1800071ac  push    rdi
0x1800071ad  push    r12
0x1800071af  push    r13
0x1800071b1  push    r14
0x1800071b3  push    r15
0x1800071b5  sub     rsp, 28h
0x1800071b9  mov     r12b, r9b
0x1800071bc  mov     r13d, r8d
0x1800071bf  mov     rbp, rdx
0x1800071c2  mov     rdi, rcx
0x1800071c5  test    rdx, rdx
0x1800071c8  jnz     short loc_1800071D4
0x1800071ca  mov     eax, 80070057h
0x1800071cf  jmp     loc_180007304
0x1800071d4  mov     qword ptr [rcx+8], 0
0x1800071dc  mov     esi, 80070057h
0x1800071e1  mov     rcx, rbp; pSid
0x1800071e4  call    cs:__imp_IsValidSid
0x1800071ea  test    eax, eax
0x1800071ec  jz      loc_180007300
0x1800071f2  mov     rcx, rbp; pSid
0x1800071f5  call    cs:__imp_GetLengthSid
0x1800071fb  mov     edx, eax; uBytes
0x1800071fd  mov     ecx, 40h ; '@'; uFlags
0x180007202  mov     ebx, eax
0x180007204  mov     esi, 8007000Eh
0x180007209  call    cs:__imp_LocalAlloc
0x18000720f  mov     r14, rax
0x180007212  test    rax, rax
0x180007215  jz      loc_180007300
0x18000721b  mov     r8, rbp; pSourceSid
0x18000721e  mov     rdx, rax; pDestinationSid
0x180007221  mov     ecx, ebx; nDestinationSidLength
0x180007223  call    cs:__imp_CopySid
0x180007229  test    eax, eax
0x18000722b  jnz     short loc_18000725A
0x18000722d  call    cs:__imp_GetLastError
0x180007233  mov     ebx, eax
0x180007235  test    eax, eax
0x180007237  jle     short loc_180007242
0x180007239  movzx   ebx, ax
0x18000723c  or      ebx, 80070000h
0x180007242  test    ebx, ebx
0x180007244  mov     eax, 80004005h
0x180007249  mov     rcx, r14; hMem
0x18000724c  cmovns  ebx, eax
0x18000724f  call    cs:__imp_LocalFree
0x180007255  jmp     loc_180007302
0x18000725a  movzx   r15d, [rsp+68h+arg_28]
0x180007263  xor     ebx, ebx
0x180007265  mov     [rdi+8], r14
0x180007269  mov     r14, [rsp+68h+Src]
0x180007271  test    r14, r14
0x180007274  jz      short loc_1800072B2
0x180007276  mov     rcx, rbp; pSid
0x180007279  call    cs:__imp_GetLengthSid
0x18000727f  lea     edx, [rax+8]
0x180007282  mov     eax, r15d
0x180007285  cmp     r15d, edx
0x180007288  jbe     short loc_1800072B2
0x18000728a  sub     eax, edx
0x18000728c  lea     ecx, [rbx+40h]; uFlags
0x18000728f  mov     edx, eax; uBytes
0x180007291  mov     [rdi+18h], edx
0x180007294  call    cs:__imp_LocalAlloc
0x18000729a  mov     [rdi+10h], rax
0x18000729e  test    rax, rax
0x1800072a1  jz      short loc_180007300
0x1800072a3  mov     r8d, [rdi+18h]; Size
0x1800072a7  mov     rdx, r14; Src
0x1800072aa  mov     rcx, rax; void *
0x1800072ad  call    memcpy_0
0x1800072b2  mov     al, [rsp+68h+arg_20]
0x1800072b9  lea     rcx, [rdi+4]; AccessMask
0x1800072bd  lea     rdx, GenericMapping; GenericMapping
0x1800072c4  mov     [rdi], al
0x1800072c6  mov     [rcx], r13d
0x1800072c9  mov     [rdi+1], r12b
0x1800072cd  mov     [rdi+2], r15w
0x1800072d2  call    cs:__imp_RtlMapGenericMask
0x1800072d8  cmp     byte ptr [rdi], 0
0x1800072db  mov     eax, 80000000h
0x1800072e0  mov     [rdi+1Ch], eax
0x1800072e3  jz      short loc_1800072EA
0x1800072e5  cmp     byte ptr [rdi], 9
0x1800072e8  jnz     short loc_1800072F2
0x1800072ea  mov     eax, 80000001h
0x1800072ef  mov     [rdi+1Ch], eax
0x1800072f2  test    byte ptr [rdi+1], 10h
0x1800072f6  jz      short loc_180007302
0x1800072f8  or      eax, 20h
0x1800072fb  mov     [rdi+1Ch], eax
0x1800072fe  jmp     short loc_180007302
0x180007300  mov     ebx, esi
0x180007302  mov     eax, ebx
0x180007304  add     rsp, 28h
0x180007308  pop     r15
0x18000730a  pop     r14
0x18000730c  pop     r13
0x18000730e  pop     r12
0x180007310  pop     rdi
0x180007311  pop     rsi
0x180007312  pop     rbp
0x180007313  pop     rbx
0x180007314  retn
```
