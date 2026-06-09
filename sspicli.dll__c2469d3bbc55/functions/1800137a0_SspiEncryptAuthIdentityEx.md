# SspiEncryptAuthIdentityEx

- ea: `0x1800137a0`
- end: `0x180013a09`
- name: `SspiEncryptAuthIdentityEx`
- size: `617`
- prototype: `SECURITY_STATUS __stdcall(ULONG Options, PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001fc10`

## callees

- `0x180005cc0`
- `0x1800078a0`
- `0x18000a170`
- `0x1800137a0`
- `0x1800154e4`

## import_xrefs

- `CRYPTBASE!SystemFunction040` at `0x1800138a0`
- `CRYPTBASE!SystemFunction040` at `0x180013999`
- `CRYPTBASE!SystemFunction040` at `0x1800139bb`
- `CRYPTBASE!SystemFunction040` at `0x1800139de`
- `CRYPTBASE!SystemFunction040` at `0x1800138a0`
- `CRYPTBASE!SystemFunction040` at `0x180013999`
- `CRYPTBASE!SystemFunction040` at `0x1800139bb`
- `CRYPTBASE!SystemFunction040` at `0x1800139de`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiEncryptAuthIdentityEx(ULONG Options, PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData)
{
  int v3; // r14d
  ULONG v4; // r15d
  SECURITY_STATUS v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  char *v9; // r8
  __int64 v10; // rax
  ULONG v11; // edx
  unsigned int v12; // ecx
  __int64 v13; // rcx
  char *v14; // rcx
  NTSTATUS v15; // eax
  bool v16; // zf
  char *v17; // rdi
  int v18; // ebx
  int ThreadLogonContext; // eax
  int v21; // edx
  int v22; // esi
  NTSTATUS v23; // eax
  int v24; // edx
  NTSTATUS v25; // eax
  int v26; // edx
  NTSTATUS v27; // eax
  ULONG OptionFlags; // [rsp+78h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+80h] [rbp+50h] BYREF
  int v30; // [rsp+88h] [rbp+58h] BYREF

  v3 = 0;
  v4 = 0;
  v30 = 0;
  OptionFlags = 0;
  v29 = 0;
  v6 = SspiValidateAuthIdentity(AuthData);
  v7 = (unsigned int)v6;
  if ( v6 < 0 )
    return SspNtStatusToSecStatus(v7);
  if ( ((Options - 1) & 0xFFFFFFFC) != 0 || Options == 3 )
    goto LABEL_48;
  if ( *(_DWORD *)AuthData != 513 )
  {
    v16 = *(_DWORD *)AuthData == 512;
    v17 = (char *)AuthData + 8;
    OptionFlags = 0;
    if ( !v16 )
      v17 = (char *)AuthData;
    v18 = *((_DWORD *)v17 + 11);
    if ( (v18 & 0x10000) == 0 )
      goto LABEL_48;
    if ( Options == 1 )
    {
      if ( (v18 & 0x10) != 0 )
        return SspNtStatusToSecStatus(3221225659LL);
      ThreadLogonContext = SecpGetThreadLogonContext((int *)&OptionFlags);
      v7 = (unsigned int)ThreadLogonContext;
      if ( ThreadLogonContext < 0 )
      {
LABEL_37:
        if ( (int)v7 < 0 )
          return SspNtStatusToSecStatus(v7);
        if ( !v3 )
        {
          *((_DWORD *)v17 + 11) = v18;
          return SspNtStatusToSecStatus(v7);
        }
        v22 = ((*((_DWORD *)v17 + 11) & 1) == 0) + 1;
        if ( *((_DWORD *)v17 + 10) )
        {
          v23 = SystemFunction040(*((PVOID *)v17 + 4), (*((_DWORD *)v17 + 10) * v22 + 7) & 0xFFFFFFF8, v4);
          v7 = (unsigned int)v23;
          if ( v23 < 0 )
            return SspNtStatusToSecStatus(v7);
        }
        v24 = *((_DWORD *)v17 + 2);
        if ( v24 )
        {
          v25 = SystemFunction040(*(PVOID *)v17, (v22 * v24 + 7) & 0xFFFFFFF8, v4);
          v7 = (unsigned int)v25;
          if ( v25 < 0 )
            return SspNtStatusToSecStatus(v7);
        }
        v26 = *((_DWORD *)v17 + 6);
        if ( v26 )
        {
          v27 = SystemFunction040(*((PVOID *)v17 + 2), (v22 * v26 + 7) & 0xFFFFFFF8, v4);
          v7 = (unsigned int)v27;
          if ( v27 < 0 )
            return SspNtStatusToSecStatus(v7);
        }
        *((_DWORD *)v17 + 11) = v18;
        return SspNtStatusToSecStatus(0);
      }
      v21 = OptionFlags != 0 ? 32 : 64;
      if ( (v18 & 0x60) != 0 )
      {
        if ( (v18 & v21) == 0 )
          return SspNtStatusToSecStatus(3221225659LL);
      }
      else
      {
        v3 = 1;
      }
      v4 = 2;
    }
    else
    {
      v7 = 0;
      if ( Options == 2 )
      {
        v21 = 16;
        if ( (v18 & 0x10) == 0 )
          v3 = 1;
      }
      else
      {
        v4 = 4;
        if ( Options != 4 )
          goto LABEL_48;
        v21 = 128;
        if ( (v18 & 0x80) == 0 )
          v3 = 1;
      }
    }
    v18 |= v21;
    goto LABEL_37;
  }
  v8 = SecpCombineAuthIdentityEncryptionFlags(Options, *((_DWORD *)AuthData + 9), &v29, &OptionFlags, &v30);
  v7 = (unsigned int)v8;
  if ( v8 >= 0 )
  {
    if ( !v30 )
    {
      *((_DWORD *)AuthData + 9) = v29;
      return SspNtStatusToSecStatus(v7);
    }
    if ( !*((_DWORD *)AuthData + 7) )
      goto LABEL_17;
    v9 = (char *)AuthData + *((unsigned int *)AuthData + 7);
    v10 = *((unsigned int *)v9 + 5);
    v11 = (*((unsigned __int16 *)v9 + 12) + 7) & 0xFFFFFFF8;
    if ( (unsigned int)v10 + v11 >= (unsigned int)v10 )
    {
      v12 = *((unsigned __int16 *)v9 + 1);
      if ( (unsigned int)v10 + v11 <= v12 && (unsigned __int16)v12 <= *((_WORD *)AuthData + 16) )
      {
        if ( Options == 2 )
        {
          v13 = *((unsigned __int16 *)AuthData + 2);
          v11 = (*((_DWORD *)AuthData + 2) - v13 + 7) & 0xFFFFFFF8;
          v14 = (char *)AuthData + v13;
        }
        else
        {
          if ( !(_DWORD)v10 )
          {
LABEL_17:
            *((_DWORD *)AuthData + 9) = v29;
            return SspNtStatusToSecStatus(0);
          }
          v14 = &v9[v10];
        }
        v15 = SystemFunction040(v14, v11, OptionFlags);
        v7 = (unsigned int)v15;
        if ( v15 < 0 )
          return SspNtStatusToSecStatus(v7);
        goto LABEL_17;
      }
    }
LABEL_48:
    v7 = 3221225485LL;
  }
  return SspNtStatusToSecStatus(v7);
}

```

## disassembly

```asm
0x1800137a0  push    rbp
0x1800137a2  push    rbx
0x1800137a3  push    rsi
0x1800137a4  push    rdi
0x1800137a5  push    r13
0x1800137a7  push    r14
0x1800137a9  push    r15
0x1800137ab  mov     rbp, rsp
0x1800137ae  sub     rsp, 30h
0x1800137b2  mov     esi, ecx
0x1800137b4  xor     r14d, r14d
0x1800137b7  xor     r15d, r15d
0x1800137ba  mov     [rbp+arg_18], r14d
0x1800137be  mov     rcx, rdx; AuthData
0x1800137c1  mov     [rbp+OptionFlags], r15d
0x1800137c5  mov     [rbp+arg_10], r14d
0x1800137c9  mov     rbx, rdx
0x1800137cc  call    SspiValidateAuthIdentity
0x1800137d1  mov     ecx, eax
0x1800137d3  test    eax, eax
0x1800137d5  js      loc_1800139F6
0x1800137db  lea     eax, [rsi-1]
0x1800137de  test    eax, 0FFFFFFFCh
0x1800137e3  jnz     loc_1800139F1
0x1800137e9  cmp     esi, 3
0x1800137ec  jz      loc_1800139F1
0x1800137f2  cmp     dword ptr [rbx], 201h
0x1800137f8  jnz     loc_1800138BB
0x1800137fe  mov     edx, [rbx+24h]; unsigned int
0x180013801  lea     rax, [rbp+arg_18]
0x180013805  lea     r9, [rbp+OptionFlags]; unsigned int *
0x180013809  mov     [rsp+30h+var_10], rax; int *
0x18001380e  lea     r8, [rbp+arg_10]; unsigned int *
0x180013812  mov     ecx, esi; unsigned int
0x180013814  call    ?SecpCombineAuthIdentityEncryptionFlags@@YAJKKPEAK0PEAH@Z; SecpCombineAuthIdentityEncryptionFlags(ulong,ulong,ulong *,ulong *,int *)
0x180013819  mov     ecx, eax
0x18001381b  test    eax, eax
0x18001381d  js      loc_1800139F6
0x180013823  cmp     [rbp+arg_18], r14d
0x180013827  jnz     short loc_180013834
0x180013829  mov     eax, [rbp+arg_10]
0x18001382c  mov     [rbx+24h], eax
0x18001382f  jmp     loc_1800139F6
0x180013834  cmp     [rbx+1Ch], r14d
0x180013838  jz      short loc_1800138B0
0x18001383a  mov     r8d, [rbx+1Ch]
0x18001383e  mov     r14d, 0FFFFFFF8h
0x180013844  add     r8, rbx
0x180013847  mov     eax, [r8+14h]
0x18001384b  movzx   edx, word ptr [r8+18h]
0x180013850  add     edx, 7
0x180013853  and     edx, r14d; MemorySize
0x180013856  lea     r9d, [rax+rdx]
0x18001385a  cmp     r9d, eax
0x18001385d  jb      loc_1800139F1
0x180013863  movzx   ecx, word ptr [r8+2]
0x180013868  cmp     r9d, ecx
0x18001386b  ja      loc_1800139F1
0x180013871  cmp     cx, [rbx+20h]
0x180013875  ja      loc_1800139F1
0x18001387b  cmp     esi, 2
0x18001387e  jnz     short loc_180013894
0x180013880  movzx   ecx, word ptr [rbx+4]
0x180013884  mov     edx, [rbx+8]
0x180013887  sub     edx, ecx
0x180013889  add     edx, 7
0x18001388c  and     edx, r14d
0x18001388f  add     rcx, rbx
0x180013892  jmp     short loc_18001389C
0x180013894  test    eax, eax
0x180013896  jz      short loc_1800138B0
0x180013898  lea     rcx, [r8+rax]; Memory
0x18001389c  mov     r8d, [rbp+OptionFlags]; OptionFlags
0x1800138a0  call    cs:__imp_SystemFunction040
0x1800138a6  mov     ecx, eax
0x1800138a8  test    eax, eax
0x1800138aa  js      loc_1800139F6
0x1800138b0  mov     eax, [rbp+arg_10]
0x1800138b3  mov     [rbx+24h], eax
0x1800138b6  jmp     loc_1800139ED
0x1800138bb  cmp     dword ptr [rbx], 200h
0x1800138c1  lea     rdi, [rbx+8]
0x1800138c5  mov     [rbp+OptionFlags], r14d
0x1800138c9  cmovnz  rdi, rbx
0x1800138cd  mov     ebx, [rdi+2Ch]
0x1800138d0  bt      ebx, 10h
0x1800138d4  jnb     loc_1800139F1
0x1800138da  mov     r13d, 1
0x1800138e0  cmp     esi, r13d
0x1800138e3  jnz     short loc_180013929
0x1800138e5  lea     edx, [r13+0Fh]
0x1800138e9  test    dl, bl
0x1800138eb  jz      short loc_1800138F7
0x1800138ed  mov     ecx, 0C00000BBh
0x1800138f2  jmp     loc_1800139F6
0x1800138f7  lea     rcx, [rbp+OptionFlags]; int *
0x1800138fb  call    ?SecpGetThreadLogonContext@@YAJPEAH@Z; SecpGetThreadLogonContext(int *)
0x180013900  mov     ecx, eax
0x180013902  test    eax, eax
0x180013904  js      short loc_18001395B
0x180013906  mov     eax, [rbp+OptionFlags]
0x180013909  neg     eax
0x18001390b  sbb     edx, edx
0x18001390d  and     edx, 0FFFFFFE0h
0x180013910  add     edx, 40h ; '@'
0x180013913  test    bl, 60h
0x180013916  jz      short loc_18001391E
0x180013918  test    edx, ebx
0x18001391a  jnz     short loc_180013921
0x18001391c  jmp     short loc_1800138ED
0x18001391e  mov     r14d, r13d
0x180013921  mov     r15d, 2
0x180013927  jmp     short loc_180013959
0x180013929  xor     ecx, ecx
0x18001392b  cmp     esi, 2
0x18001392e  jnz     short loc_180013940
0x180013930  lea     edx, [rcx+10h]
0x180013933  mov     eax, ebx
0x180013935  and     eax, edx
0x180013937  test    al, al
0x180013939  jnz     short loc_180013959
0x18001393b  mov     r14d, r13d
0x18001393e  jmp     short loc_180013959
0x180013940  mov     r15d, 4
0x180013946  cmp     esi, r15d
0x180013949  jnz     loc_1800139F1
0x18001394f  lea     edx, [r15+7Ch]
0x180013953  test    dl, bl
0x180013955  cmovz   r14d, r13d
0x180013959  or      ebx, edx
0x18001395b  test    ecx, ecx
0x18001395d  js      loc_1800139F6
0x180013963  test    r14d, r14d
0x180013966  jnz     short loc_180013970
0x180013968  mov     [rdi+2Ch], ebx
0x18001396b  jmp     loc_1800139F6
0x180013970  mov     esi, [rdi+2Ch]
0x180013973  mov     r14d, 0FFFFFFF8h
0x180013979  not     esi
0x18001397b  and     esi, r13d
0x18001397e  inc     esi
0x180013980  cmp     dword ptr [rdi+28h], 0
0x180013984  jz      short loc_1800139A5
0x180013986  mov     rcx, [rdi+20h]; Memory
0x18001398a  mov     edx, esi
0x18001398c  imul    edx, [rdi+28h]
0x180013990  mov     r8d, r15d; OptionFlags
0x180013993  add     edx, 7
0x180013996  and     edx, r14d; MemorySize
0x180013999  call    cs:__imp_SystemFunction040
0x18001399f  mov     ecx, eax
0x1800139a1  test    eax, eax
0x1800139a3  js      short loc_1800139F6
0x1800139a5  mov     edx, [rdi+8]
0x1800139a8  test    edx, edx
0x1800139aa  jz      short loc_1800139C7
0x1800139ac  mov     rcx, [rdi]; Memory
0x1800139af  mov     r8d, r15d; OptionFlags
0x1800139b2  imul    edx, esi
0x1800139b5  add     edx, 7
0x1800139b8  and     edx, r14d; MemorySize
0x1800139bb  call    cs:__imp_SystemFunction040
0x1800139c1  mov     ecx, eax
0x1800139c3  test    eax, eax
0x1800139c5  js      short loc_1800139F6
0x1800139c7  mov     edx, [rdi+18h]
0x1800139ca  test    edx, edx
0x1800139cc  jz      short loc_1800139EA
0x1800139ce  mov     rcx, [rdi+10h]; Memory
0x1800139d2  mov     r8d, r15d; OptionFlags
0x1800139d5  imul    edx, esi
0x1800139d8  add     edx, 7
0x1800139db  and     edx, r14d; MemorySize
0x1800139de  call    cs:__imp_SystemFunction040
0x1800139e4  mov     ecx, eax
0x1800139e6  test    eax, eax
0x1800139e8  js      short loc_1800139F6
0x1800139ea  mov     [rdi+2Ch], ebx
0x1800139ed  xor     ecx, ecx
0x1800139ef  jmp     short loc_1800139F6
0x1800139f1  mov     ecx, 0C000000Dh
0x1800139f6  add     rsp, 30h
0x1800139fa  pop     r15
0x1800139fc  pop     r14
0x1800139fe  pop     r13
0x180013a00  pop     rdi
0x180013a01  pop     rsi
0x180013a02  pop     rbx
0x180013a03  pop     rbp
0x180013a04  jmp     SspNtStatusToSecStatus
```
