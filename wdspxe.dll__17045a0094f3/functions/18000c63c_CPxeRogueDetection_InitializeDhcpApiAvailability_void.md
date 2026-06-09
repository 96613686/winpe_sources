# CPxeRogueDetection::InitializeDhcpApiAvailability(void)

- ea: `0x18000c63c`
- end: `0x18000c7eb`
- name: `?InitializeDhcpApiAvailability@CPxeRogueDetection@@AEAAXXZ`
- size: `431`
- prototype: `void __fastcall(CPxeRogueDetection *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000c494`

## callees

- `0x180002a30`
- `0x18000c63c`
- `0x180011470`

## string_xrefs

- `0x18000c698`: `DHCPSAPI.DLL`

## pseudocode

```c
void __fastcall CPxeRogueDetection::InitializeDhcpApiAvailability(CPxeRogueDetection *this)
{
  int v2; // r9d
  int v3; // ebx
  const ImgDelayDescr *i; // rsi
  _BYTE *v5; // r8
  _BYTE *v6; // rcx
  __int64 v8; // rcx
  const char *v9; // rdx
  const char *v11; // rdx
  char *v12; // rdi
  int v13; // ecx
  char *j; // rax
  char *v15; // r14

  v2 = -2147024770;
  v3 = 0;
  if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 180] )
  {
    for ( i = (const ImgDelayDescr *)((char *)&_ImageBase + *(unsigned int *)&byte_180000040[(int)off_18000003C + 176]);
          i->rvaDLLName;
          ++i )
    {
      v5 = (char *)&_ImageBase + i->rvaDLLName;
      v6 = v5;
      while ( *v6++ )
        ;
      v8 = v6 - v5 - 1;
      v9 = "DHCPSAPI.DLL";
      while ( *v9++ )
        ;
      if ( v8 == v9 - "DHCPSAPI.DLL" - 1 )
      {
        v11 = "DHCPSAPI.DLL";
        if ( !v8 )
          goto LABEL_26;
        while ( --v8 && *v11 == *v5 )
        {
          ++v11;
          ++v5;
        }
        if ( *(unsigned __int8 *)v11 == (unsigned __int8)*v5 )
        {
LABEL_26:
          if ( i->rvaDLLName )
          {
            v12 = (char *)&_ImageBase + i->rvaIAT;
            v13 = 0;
            for ( j = v12; *(_QWORD *)j; j += 8 )
              ++v13;
            v15 = &v12[8 * v13];
            while ( v12 < v15 )
            {
              _delayLoadHelper2(i, v12);
              v12 += 8;
            }
            v2 = 0;
          }
          break;
        }
      }
    }
  }
  LOBYTE(v3) = v2 >= 0;
  *((_DWORD *)this + 18) = v3;
}

```

## disassembly

```asm
0x18000c63c  mov     [rsp+arg_10], rbx
0x18000c641  mov     [rsp+arg_18], rsi
0x18000c646  mov     [rsp+arg_0], rcx
0x18000c64b  push    rdi
0x18000c64c  push    r14
0x18000c64e  push    r15
0x18000c650  sub     rsp, 80h
0x18000c657  mov     r15, rcx
0x18000c65a  mov     r9d, 8007007Eh
0x18000c660  mov     [rsp+98h+var_6C], r9d
0x18000c665  movsxd  rax, cs:off_18000003C
0x18000c66c  lea     r10, __ImageBase
0x18000c673  xor     ebx, ebx
0x18000c675  cmp     [rax+r10+0F4h], ebx
0x18000c67d  jz      loc_18000C7A7
0x18000c683  mov     [rsp+98h+var_68], rbx
0x18000c688  mov     esi, [rax+r10+0F0h]
0x18000c690  add     rsi, r10
0x18000c693  mov     [rsp+98h+var_68], rsi
0x18000c698  lea     r11, aDhcpsapiDll_0; "DHCPSAPI.DLL"
0x18000c69f  cmp     [rsi+4], ebx
0x18000c6a2  jz      loc_18000C7A7
0x18000c6a8  mov     r8d, [rsi+4]
0x18000c6ac  add     r8, r10
0x18000c6af  mov     rcx, r8
0x18000c6b2  mov     [rsp+98h+var_58], rcx
0x18000c6b7  mov     al, [rcx]
0x18000c6b9  inc     rcx
0x18000c6bc  mov     [rsp+98h+var_58], rcx
0x18000c6c1  test    al, al
0x18000c6c3  jz      short loc_18000C6C7
0x18000c6c5  jmp     short loc_18000C6B7
0x18000c6c7  sub     rcx, r8
0x18000c6ca  dec     rcx
0x18000c6cd  mov     rdx, r11
0x18000c6d0  mov     [rsp+98h+var_50], rdx
0x18000c6d5  mov     al, [rdx]
0x18000c6d7  inc     rdx
0x18000c6da  mov     [rsp+98h+var_50], rdx
0x18000c6df  test    al, al
0x18000c6e1  jz      short loc_18000C6E5
0x18000c6e3  jmp     short loc_18000C6D5
0x18000c6e5  sub     rdx, r11
0x18000c6e8  dec     rdx
0x18000c6eb  cmp     rcx, rdx
0x18000c6ee  jnz     short loc_18000C73D
0x18000c6f0  mov     [rsp+98h+var_48], rcx
0x18000c6f5  mov     [rsp+98h+var_38], r8
0x18000c6fa  mov     rdx, r11
0x18000c6fd  mov     [rsp+98h+var_40], rdx
0x18000c702  test    rcx, rcx
0x18000c705  jz      short loc_18000C74B
0x18000c707  sub     rcx, 1
0x18000c70b  mov     [rsp+98h+var_48], rcx
0x18000c710  jz      short loc_18000C72B
0x18000c712  mov     al, [r8]
0x18000c715  cmp     [rdx], al
0x18000c717  jnz     short loc_18000C72B
0x18000c719  inc     rdx
0x18000c71c  mov     [rsp+98h+var_40], rdx
0x18000c721  inc     r8
0x18000c724  mov     [rsp+98h+var_38], r8
0x18000c729  jmp     short loc_18000C707
0x18000c72b  movzx   eax, byte ptr [r8]
0x18000c72f  movzx   ecx, byte ptr [rdx]
0x18000c732  sub     ecx, eax
0x18000c734  mov     [rsp+98h+arg_8], ecx
0x18000c73b  jz      short loc_18000C74B
0x18000c73d  add     rsi, 20h ; ' '
0x18000c741  mov     [rsp+98h+var_68], rsi
0x18000c746  jmp     loc_18000C69F
0x18000c74b  cmp     [rsi+4], ebx
0x18000c74e  jz      short loc_18000C7A7
0x18000c750  mov     edi, [rsi+0Ch]
0x18000c753  add     rdi, r10
0x18000c756  mov     [rsp+98h+var_28], rdi
0x18000c75b  mov     ecx, ebx
0x18000c75d  mov     [rsp+98h+var_70], ebx
0x18000c761  mov     rax, rdi
0x18000c764  mov     [rsp+98h+var_30], rax
0x18000c769  cmp     [rax], rbx
0x18000c76c  jz      short loc_18000C77F
0x18000c76e  add     rax, 8
0x18000c772  mov     [rsp+98h+var_30], rax
0x18000c777  inc     ecx
0x18000c779  mov     [rsp+98h+var_70], ecx
0x18000c77d  jmp     short loc_18000C769
0x18000c77f  mov     eax, ecx
0x18000c781  lea     r14, [rdi+rax*8]
0x18000c785  cmp     rdi, r14
0x18000c788  jnb     short loc_18000C7A0
0x18000c78a  mov     rdx, rdi
0x18000c78d  mov     rcx, rsi
0x18000c790  call    __delayLoadHelper2
0x18000c795  add     rdi, 8
0x18000c799  mov     [rsp+98h+var_28], rdi
0x18000c79e  jmp     short loc_18000C785
0x18000c7a0  mov     r9d, ebx
0x18000c7a3  mov     [rsp+98h+var_6C], ebx
0x18000c7a7  test    r9d, r9d
0x18000c7aa  setns   bl
0x18000c7ad  mov     [r15+48h], ebx
0x18000c7b1  jmp     short loc_18000C7D1
0x18000c7b3  mov     rax, [rsp+98h+arg_0]
0x18000c7bb  and     dword ptr [rax+48h], 0
0x18000c7bf  lea     rdx, aRogueDetection_10; "Rogue Detection: DHCP API library not f"...
0x18000c7c6  mov     ecx, 80000h; unsigned int
0x18000c7cb  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000c7d0  nop
0x18000c7d1  lea     r11, [rsp+98h+var_18]
0x18000c7d9  mov     rbx, [r11+30h]
0x18000c7dd  mov     rsi, [r11+38h]
0x18000c7e1  mov     rsp, r11
0x18000c7e4  pop     r15
0x18000c7e6  pop     r14
0x18000c7e8  pop     rdi
0x18000c7e9  retn
0x180011f75  push    rbp
0x180011f77  sub     rsp, 20h
0x180011f7b  mov     rbp, rdx
0x180011f7e  mov     [rbp+78h], rcx
0x180011f82  mov     rax, [rcx]
0x180011f85  mov     ecx, [rax]
0x180011f87  mov     [rbp+38h], ecx
0x180011f8a  mov     [rbp+20h], ecx
0x180011f8d  mov     eax, [rbp+20h]
0x180011f90  cmp     eax, 0C06D007Eh
0x180011f95  jz      short loc_180011FA5
0x180011f97  mov     eax, [rbp+20h]
0x180011f9a  cmp     eax, 0C06D007Fh
0x180011f9f  jz      short loc_180011FA5
0x180011fa1  xor     eax, eax
0x180011fa3  jmp     short loc_180011FAA
0x180011fa5  mov     eax, 1
0x180011faa  add     rsp, 20h
0x180011fae  pop     rbp
0x180011faf  retn
```
