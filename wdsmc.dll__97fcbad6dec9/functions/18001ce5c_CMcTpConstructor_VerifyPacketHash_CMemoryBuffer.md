# CMcTpConstructor::VerifyPacketHash(CMemoryBuffer *)

- ea: `0x18001ce5c`
- end: `0x18001d06c`
- name: `?VerifyPacketHash@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(CMcTpConstructor *this, struct CMemoryBuffer *, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015c34`

## callees

- `0x18001a9a8`
- `0x18001ce5c`
- `0x1800227d4`
- `0x180025850`
- `0x180025f3c`
- `0x180025f94`
- `0x18002607c`
- `0x180026d22`
- `0x180026d3a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001cf6d`
- `KERNEL32!GetLastError` at `0x18001cf6d`
- `ADVAPI32!CryptHashData` at `0x18001cf63`
- `ADVAPI32!CryptHashData` at `0x18001cf63`
- `WS2_32!__imp_ntohs` at `0x18001cef1`
- `WS2_32!__imp_ntohs` at `0x18001cef1`

## string_xrefs

- `0x18001cea7`: `((((m_uSecurityMode) & 0xffff) == (1)) || ((((m_uSecurityMode)>>16)&0xffff) == (1)))`

## pseudocode

```c
__int64 __fastcall CMcTpConstructor::VerifyPacketHash(
        CMcTpConstructor *this,
        struct CMemoryBuffer *a2,
        __int64 a3,
        int a4)
{
  __int64 v4; // rdi
  int v6; // ecx
  unsigned int v8; // esi
  unsigned int Hash; // ebx
  __int64 v10; // r12
  int v11; // r13d
  unsigned int v12; // ecx
  DWORD v13; // esi
  const BYTE *v14; // rdi
  struct CCryptKey *v15; // r8
  struct CCryptStore *v16; // rdx
  const char *v17; // rdx
  const char *v18; // rdx
  DWORD LastError; // eax
  const char *v20; // rdx
  const char *v21; // rdx
  const char *v22; // rdx
  __int64 v24; // [rsp+30h] [rbp-10h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-8h]
  size_t Size; // [rsp+70h] [rbp+30h] BYREF
  void *Buf2; // [rsp+78h] [rbp+38h] BYREF

  v4 = *((_QWORD *)a2 + 5);
  v6 = *(_DWORD *)this;
  v8 = *((_DWORD *)a2 + 12);
  v24 = 0;
  hHash = 0;
  if ( (unsigned __int16)v6 != 1 && HIWORD(v6) != 1 )
    WdsAssert(
      "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp",
      0x1CEu,
      "((((m_uSecurityMode) & 0xffff) == (1)) || ((((m_uSecurityMode)>>16)&0xffff) == (1)))",
      a4,
      0);
  if ( v8 < 5 )
    goto LABEL_5;
  v10 = v4;
  if ( *(_WORD *)v4 != *(_WORD *)"WD" )
    goto LABEL_5;
  if ( *(_BYTE *)(v4 + 2) != 2 )
  {
    Hash = -1054801652;
    goto LABEL_25;
  }
  v11 = ntohs(*(_WORD *)(v4 + 3));
  v12 = v11 + 5;
  if ( v8 >= v11 + 5 )
  {
    v13 = v8 - v12;
    v14 = (const BYTE *)(v12 + v4);
    if ( *((_DWORD *)this + 24) )
    {
      v15 = (struct CCryptKey *)*((_QWORD *)this + 3);
      v16 = (struct CCryptStore *)*((_QWORD *)v15 + 1);
    }
    else
    {
      v16 = (CMcTpConstructor *)((char *)this + 32);
      v15 = (CMcTpConstructor *)((char *)this + 64);
    }
    Hash = CCryptHMAC::CreateHash((CCryptHMAC *)&v24, v16, v15, *((_DWORD *)this + 23), *((_DWORD *)this + 22));
    if ( !ElValidateWin32(Hash, v17, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x20Du) )
    {
      Hash = 0;
      if ( !CryptHashData(hHash, v14, v13, 0) )
      {
        LastError = GetLastError();
        Hash = ElValidateWin32(LastError, v20, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthash.cpp", 0xF7u);
      }
      if ( !ElValidateWin32(Hash, v18, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x214u) )
      {
        Buf2 = 0;
        LODWORD(Size) = 0;
        Hash = CCryptHash::GetHashValue((CCryptHash *)&v24, &Buf2, (unsigned int *)&Size);
        if ( !ElValidateWin32(Hash, v21, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthash.cpp", 0x11Cu)
          && (v11 != (_DWORD)Size || memcmp_0((const void *)(v10 + 5), Buf2, (unsigned int)Size)) )
        {
          Hash = ElValidateWin32(0xDu, v22, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthash.cpp", 0x124u);
        }
        if ( Buf2 )
          operator delete(Buf2);
        if ( !ElValidateWin32(Hash, v22, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x21Bu) )
        {
          memmove_0(*((void **)a2 + 5), v14, v13);
          *((_DWORD *)a2 + 12) = v13;
        }
      }
    }
  }
  else
  {
LABEL_5:
    Hash = 13;
  }
LABEL_25:
  CCryptHash::DestroyHash((CCryptHash *)&v24);
  return Hash;
}

```

## disassembly

```asm
0x18001ce5c  mov     [rsp-28h+arg_10], rbx
0x18001ce61  mov     [rsp-28h+arg_18], rsi
0x18001ce66  push    rbp
0x18001ce67  push    rdi
0x18001ce68  push    r12
0x18001ce6a  push    r13
0x18001ce6c  push    r15
0x18001ce6e  mov     rbp, rsp
0x18001ce71  sub     rsp, 40h
0x18001ce75  mov     rdi, [rdx+28h]
0x18001ce79  mov     rbx, rcx
0x18001ce7c  mov     ecx, [rcx]
0x18001ce7e  mov     r15, rdx
0x18001ce81  mov     esi, [rdx+30h]
0x18001ce84  mov     edx, 1
0x18001ce89  and     [rbp+var_10], 0
0x18001ce8e  and     [rbp+hHash], 0
0x18001ce93  movzx   eax, cx
0x18001ce96  cmp     eax, edx
0x18001ce98  jz      short loc_18001CEBF
0x18001ce9a  shr     ecx, 10h
0x18001ce9d  cmp     cx, dx
0x18001cea0  jz      short loc_18001CEBF
0x18001cea2  and     [rsp+40h+var_20], 0
0x18001cea7  lea     r8, aMUsecuritymode; "((((m_uSecurityMode) & 0xffff) == (1)) "...
0x18001ceae  mov     edx, 1CEh; unsigned int
0x18001ceb3  lea     rcx, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001ceba  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001cebf  cmp     esi, 5
0x18001cec2  jnb     short loc_18001CECE
0x18001cec4  mov     ebx, 0Dh
0x18001cec9  jmp     loc_18001D048
0x18001cece  movzx   eax, word ptr [rdi]
0x18001ced1  mov     r12, rdi
0x18001ced4  cmp     ax, word ptr cs:aWd; "WD"
0x18001cedb  jnz     short loc_18001CEC4
0x18001cedd  cmp     byte ptr [rdi+2], 2
0x18001cee1  jz      short loc_18001CEED
0x18001cee3  mov     ebx, 0C121010Ch
0x18001cee8  jmp     loc_18001D048
0x18001ceed  movzx   ecx, word ptr [rdi+3]; netshort
0x18001cef1  call    cs:__imp_ntohs
0x18001cef7  movzx   r13d, ax
0x18001cefb  lea     ecx, [r13+5]
0x18001ceff  cmp     esi, ecx
0x18001cf01  jb      short loc_18001CEC4
0x18001cf03  mov     eax, ecx
0x18001cf05  sub     esi, ecx
0x18001cf07  add     rdi, rax
0x18001cf0a  cmp     dword ptr [rbx+60h], 0
0x18001cf0e  jz      short loc_18001CF1A
0x18001cf10  mov     r8, [rbx+18h]
0x18001cf14  mov     rdx, [r8+8]
0x18001cf18  jmp     short loc_18001CF22
0x18001cf1a  lea     rdx, [rbx+20h]; struct CCryptStore *
0x18001cf1e  lea     r8, [rbx+40h]; struct CCryptKey *
0x18001cf22  mov     eax, [rbx+58h]
0x18001cf25  lea     rcx, [rbp+var_10]; this
0x18001cf29  mov     r9d, [rbx+5Ch]; unsigned int
0x18001cf2d  mov     [rsp+40h+var_20], eax; unsigned int
0x18001cf31  call    ?CreateHash@CCryptHMAC@@QEAAKPEAVCCryptStore@@PEAVCCryptKey@@II@Z; CCryptHMAC::CreateHash(CCryptStore *,CCryptKey *,uint,uint)
0x18001cf36  mov     r9d, 20Dh; unsigned int
0x18001cf3c  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001cf43  mov     ecx, eax; unsigned int
0x18001cf45  mov     ebx, eax
0x18001cf47  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001cf4c  test    eax, eax
0x18001cf4e  jnz     loc_18001D048
0x18001cf54  mov     rcx, [rbp+hHash]; hHash
0x18001cf58  xor     r9d, r9d; dwFlags
0x18001cf5b  mov     r8d, esi; dwDataLen
0x18001cf5e  mov     rdx, rdi; pbData
0x18001cf61  xor     ebx, ebx
0x18001cf63  call    cs:__imp_CryptHashData
0x18001cf69  test    eax, eax
0x18001cf6b  jnz     short loc_18001CF89
0x18001cf6d  call    cs:__imp_GetLastError
0x18001cf73  mov     r9d, 0F7h; unsigned int
0x18001cf79  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x18001cf80  mov     ecx, eax; unsigned int
0x18001cf82  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001cf87  mov     ebx, eax
0x18001cf89  mov     r9d, 214h; unsigned int
0x18001cf8f  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001cf96  mov     ecx, ebx; unsigned int
0x18001cf98  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001cf9d  test    eax, eax
0x18001cf9f  jnz     loc_18001D048
0x18001cfa5  and     [rbp+Buf2], 0
0x18001cfaa  lea     r8, [rbp+Size]; unsigned int *
0x18001cfae  and     dword ptr [rbp+Size], eax
0x18001cfb1  lea     rdx, [rbp+Buf2]; void **
0x18001cfb5  lea     rcx, [rbp+var_10]; this
0x18001cfb9  call    ?GetHashValue@CCryptHash@@QEAAKPEAPEAXPEAK@Z; CCryptHash::GetHashValue(void * *,ulong *)
0x18001cfbe  mov     r9d, 11Ch; unsigned int
0x18001cfc4  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x18001cfcb  mov     ecx, eax; unsigned int
0x18001cfcd  mov     ebx, eax
0x18001cfcf  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001cfd4  test    eax, eax
0x18001cfd6  jnz     short loc_18001D00D
0x18001cfd8  cmp     r13d, dword ptr [rbp+Size]
0x18001cfdc  jnz     short loc_18001CFF4
0x18001cfde  mov     r8d, dword ptr [rbp+Size]; Size
0x18001cfe2  lea     rcx, [r12+5]; Buf1
0x18001cfe7  mov     rdx, [rbp+Buf2]; Buf2
0x18001cfeb  call    memcmp_0
0x18001cff0  test    eax, eax
0x18001cff2  jz      short loc_18001D00D
0x18001cff4  mov     r9d, 124h; unsigned int
0x18001cffa  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x18001d001  mov     ecx, 0Dh; unsigned int
0x18001d006  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d00b  mov     ebx, eax
0x18001d00d  cmp     [rbp+Buf2], 0
0x18001d012  jz      short loc_18001D01D
0x18001d014  mov     rcx, [rbp+Buf2]; void *
0x18001d018  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d01d  mov     r9d, 21Bh; unsigned int
0x18001d023  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001d02a  mov     ecx, ebx; unsigned int
0x18001d02c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d031  test    eax, eax
0x18001d033  jnz     short loc_18001D048
0x18001d035  mov     rcx, [r15+28h]; void *
0x18001d039  mov     rdx, rdi; Src
0x18001d03c  mov     r8d, esi; Size
0x18001d03f  call    memmove_0
0x18001d044  mov     [r15+30h], esi
0x18001d048  lea     rcx, [rbp+var_10]; this
0x18001d04c  call    ?DestroyHash@CCryptHash@@QEAAKXZ; CCryptHash::DestroyHash(void)
0x18001d051  lea     r11, [rsp+40h+var_s0]
0x18001d056  mov     eax, ebx
0x18001d058  mov     rbx, [r11+40h]
0x18001d05c  mov     rsi, [r11+48h]
0x18001d060  mov     rsp, r11
0x18001d063  pop     r15
0x18001d065  pop     r13
0x18001d067  pop     r12
0x18001d069  pop     rdi
0x18001d06a  pop     rbp
0x18001d06b  retn
```
