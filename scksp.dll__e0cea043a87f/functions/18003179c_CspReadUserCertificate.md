# CspReadUserCertificate

- ea: `0x18003179c`
- end: `0x1800318e1`
- name: `CspReadUserCertificate`
- size: `325`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018968`
- `0x180031340`

## callees

- `0x18000d9d0`
- `0x18002b140`
- `0x18002db88`
- `0x18002de34`
- `0x18003179c`
- `0x180036d3c`
- `0x18003c240`

## pseudocode

```c
__int64 __fastcall CspReadUserCertificate(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  void *v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-20h] BYREF
  int v15; // [rsp+48h] [rbp-18h]

  v13 = 0;
  v14 = 0;
  v15 = 0;
  v12 = 0;
  v5 = CspReadFile(a1, "mscp", a2, 0, &v13, &v12);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 == -2146435036 )
      v6 = -2146435028;
    goto LABEL_4;
  }
  v6 = CspQueryCapabilities(a1, &v14);
  if ( v6 )
  {
LABEL_4:
    v7 = *((_QWORD *)a3 + 1);
    if ( v7 )
    {
      CspFreeH(v7);
      *((_QWORD *)a3 + 1) = 0;
    }
    goto LABEL_6;
  }
  if ( !HIDWORD(v14) )
  {
    v6 = UncompressData(v12, v13, a3, 0);
    if ( !v6 )
    {
      v10 = MIDL_user_allocate(*a3);
      *((_QWORD *)a3 + 1) = v10;
      if ( v10 )
      {
        v11 = UncompressData(v12, v13, a3, v10);
        v6 = v11;
        if ( !v11 )
        {
LABEL_6:
          v8 = v13;
          goto LABEL_7;
        }
        if ( v11 == 1359 )
          v6 = -2146893819;
      }
      else
      {
        v6 = -2146893810;
      }
    }
    goto LABEL_4;
  }
  v8 = 0;
  *a3 = v12;
  *((_QWORD *)a3 + 1) = v13;
  v13 = 0;
LABEL_7:
  if ( v8 )
    CspFreeH(v8);
  return v6;
}

```

## disassembly

```asm
0x18003179c  mov     [rsp-18h+arg_18], rbx
0x1800317a1  push    rbp
0x1800317a2  push    rsi
0x1800317a3  push    rdi
0x1800317a4  mov     rbp, rsp
0x1800317a7  sub     rsp, 60h
0x1800317ab  mov     rax, cs:__security_cookie
0x1800317b2  xor     rax, rsp
0x1800317b5  mov     [rbp+var_10], rax
0x1800317b9  xor     eax, eax
0x1800317bb  mov     [rbp+var_28], 0
0x1800317c3  mov     [rbp+var_20], rax
0x1800317c7  mov     rdi, r8
0x1800317ca  mov     [rbp+var_18], eax
0x1800317cd  mov     r8, rdx
0x1800317d0  lea     rax, [rbp+var_30]
0x1800317d4  mov     [rbp+var_30], 0
0x1800317db  mov     [rsp+60h+var_38], rax
0x1800317e0  lea     rdx, aMscp; "mscp"
0x1800317e7  lea     rax, [rbp+var_28]
0x1800317eb  xor     r9d, r9d
0x1800317ee  mov     [rsp+60h+var_40], rax
0x1800317f3  mov     rsi, rcx
0x1800317f6  call    CspReadFile
0x1800317fb  mov     ebx, eax
0x1800317fd  test    eax, eax
0x1800317ff  jz      short loc_18003184F
0x180031801  cmp     eax, 80100024h
0x180031806  jnz     short loc_18003180D
0x180031808  mov     ebx, 8010002Ch
0x18003180d  mov     rcx, [rdi+8]
0x180031811  test    rcx, rcx
0x180031814  jz      short loc_180031823
0x180031816  call    CspFreeH
0x18003181b  mov     qword ptr [rdi+8], 0
0x180031823  mov     rcx, [rbp+var_28]
0x180031827  test    rcx, rcx
0x18003182a  jz      short loc_180031831
0x18003182c  call    CspFreeH
0x180031831  mov     eax, ebx
0x180031833  mov     rcx, [rbp+var_10]
0x180031837  xor     rcx, rsp; StackCookie
0x18003183a  call    __security_check_cookie
0x18003183f  mov     rbx, [rsp+60h+arg_18]
0x180031847  add     rsp, 60h
0x18003184b  pop     rdi
0x18003184c  pop     rsi
0x18003184d  pop     rbp
0x18003184e  retn
0x18003184f  lea     rdx, [rbp+var_20]
0x180031853  mov     rcx, rsi
0x180031856  call    CspQueryCapabilities
0x18003185b  mov     ebx, eax
0x18003185d  test    eax, eax
0x18003185f  jnz     short loc_18003180D
0x180031861  cmp     dword ptr [rbp+var_20+4], eax
0x180031864  jnz     short loc_1800318C9
0x180031866  mov     rdx, [rbp+var_28]
0x18003186a  xor     r9d, r9d
0x18003186d  mov     ecx, [rbp+var_30]
0x180031870  mov     r8, rdi
0x180031873  call    UncompressData
0x180031878  mov     ebx, eax
0x18003187a  test    eax, eax
0x18003187c  jnz     short loc_18003180D
0x18003187e  mov     ecx, [rdi]; size
0x180031880  call    MIDL_user_allocate
0x180031885  mov     [rdi+8], rax
0x180031889  test    rax, rax
0x18003188c  jnz     short loc_180031898
0x18003188e  mov     ebx, 8009000Eh
0x180031893  jmp     loc_18003180D
0x180031898  mov     rdx, [rbp+var_28]
0x18003189c  mov     r9, rax
0x18003189f  mov     ecx, [rbp+var_30]
0x1800318a2  mov     r8, rdi
0x1800318a5  call    UncompressData
0x1800318aa  mov     ebx, eax
0x1800318ac  test    eax, eax
0x1800318ae  jz      loc_180031823
0x1800318b4  cmp     eax, 54Fh
0x1800318b9  jnz     loc_18003180D
0x1800318bf  mov     ebx, 80090005h
0x1800318c4  jmp     loc_18003180D
0x1800318c9  mov     eax, [rbp+var_30]
0x1800318cc  xor     ecx, ecx
0x1800318ce  mov     [rdi], eax
0x1800318d0  mov     rax, [rbp+var_28]
0x1800318d4  mov     [rdi+8], rax
0x1800318d8  mov     [rbp+var_28], rcx
0x1800318dc  jmp     loc_180031827
```
