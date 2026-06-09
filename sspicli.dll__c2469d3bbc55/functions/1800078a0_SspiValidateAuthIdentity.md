# SspiValidateAuthIdentity

- ea: `0x1800078a0`
- end: `0x1800079f0`
- name: `SspiValidateAuthIdentity`
- size: `336`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008920`
- `0x1800090e0`
- `0x18000e9d0`
- `0x1800137a0`
- `0x180020540`

## callees

- `0x180005cc0`
- `0x1800078a0`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiValidateAuthIdentity(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData)
{
  char *v1; // rdx
  unsigned int v3; // r8d
  unsigned int v4; // ecx
  unsigned int v5; // r9d
  unsigned int v6; // ecx
  unsigned int v7; // r9d
  unsigned int v8; // ecx
  unsigned int v9; // r9d
  unsigned int v10; // ecx
  __int64 v11; // r9
  unsigned int v12; // r8d
  unsigned int v13; // ecx
  unsigned int v14; // edx

  v1 = (char *)AuthData;
  if ( *(_DWORD *)AuthData == 513 )
  {
    if ( *((_WORD *)AuthData + 2) < 0x30u )
      return SspNtStatusToSecStatus(-1073741811);
    v3 = *((_DWORD *)AuthData + 2);
    if ( v3 > 0xFFF7 )
      return SspNtStatusToSecStatus(-1073741811);
    if ( v3 < *((unsigned __int16 *)AuthData + 2) )
      return SspNtStatusToSecStatus(-1073741811);
    v4 = *((unsigned __int16 *)AuthData + 12);
    v5 = v4 + *((_DWORD *)v1 + 5);
    if ( v5 > v3 )
      return SspNtStatusToSecStatus(-1073741811);
    if ( v5 < v4 )
      return SspNtStatusToSecStatus(-1073741811);
    v6 = *((unsigned __int16 *)v1 + 8);
    v7 = v6 + *((_DWORD *)v1 + 3);
    if ( v7 < v6 )
      return SspNtStatusToSecStatus(-1073741811);
    if ( v7 > v3 )
      return SspNtStatusToSecStatus(-1073741811);
    v8 = *((unsigned __int16 *)v1 + 22);
    v9 = v8 + *((_DWORD *)v1 + 10);
    if ( v9 < v8 )
      return SspNtStatusToSecStatus(-1073741811);
    if ( v9 > v3 )
      return SspNtStatusToSecStatus(-1073741811);
    v10 = *((unsigned __int16 *)v1 + 16);
    v11 = *((unsigned int *)v1 + 7);
    if ( v10 + (unsigned int)v11 < v10 || v10 + (unsigned int)v11 > v3 )
      return SspNtStatusToSecStatus(-1073741811);
    if ( (_DWORD)v11 )
    {
      if ( v10 < 0x1C )
        return SspNtStatusToSecStatus(-1073741811);
      if ( (*((_DWORD *)v1 + 9) & 0x10) == 0 )
      {
        v12 = *(unsigned __int16 *)&v1[v11 + 2];
        if ( v12 > v10 )
          return SspNtStatusToSecStatus(-1073741811);
        if ( (unsigned __int16)v12 < *(_WORD *)&v1[v11] )
          return SspNtStatusToSecStatus(-1073741811);
        if ( *(_WORD *)&v1[v11] < 0x1Cu )
          return SspNtStatusToSecStatus(-1073741811);
        v13 = *(_DWORD *)&v1[v11 + 20];
        v14 = v13 + *(unsigned __int16 *)&v1[v11 + 24];
        if ( v14 < v13 || v14 > v12 )
          return SspNtStatusToSecStatus(-1073741811);
      }
      return SspNtStatusToSecStatus(0);
    }
    if ( !(_WORD)v10 )
      return SspNtStatusToSecStatus(0);
  }
  else
  {
    if ( *(_DWORD *)AuthData == 512 )
    {
      if ( *((_DWORD *)AuthData + 1) < 0x48u || *((_DWORD *)AuthData + 16) > 0x7FFDu )
        return SspNtStatusToSecStatus(-1073741811);
      v1 = (char *)AuthData + 8;
    }
    if ( (v1[44] & 3) != 0
      && *((_DWORD *)v1 + 2) <= 0x7FFDu
      && *((_DWORD *)v1 + 6) <= 0x7FFDu
      && *((_DWORD *)v1 + 10) <= 0x7FFDu )
    {
      return SspNtStatusToSecStatus(0);
    }
  }
  return SspNtStatusToSecStatus(-1073741811);
}

```

## disassembly

```asm
0x1800078a0  xor     r10d, r10d
0x1800078a3  mov     rdx, rcx
0x1800078a6  cmp     dword ptr [rcx], 201h
0x1800078ac  jnz     short loc_1800078BF
0x1800078ae  cmp     word ptr [rcx+4], 30h ; '0'
0x1800078b3  jnb     short loc_1800078EA
0x1800078b5  mov     ecx, 0C000000Dh
0x1800078ba  jmp     SspNtStatusToSecStatus
0x1800078bf  cmp     dword ptr [rcx], 200h
0x1800078c5  mov     eax, 7FFDh
0x1800078ca  jz      loc_1800079C6
0x1800078d0  test    byte ptr [rdx+2Ch], 3
0x1800078d4  jz      short loc_1800078B5
0x1800078d6  cmp     [rdx+8], eax
0x1800078d9  ja      short loc_1800078B5
0x1800078db  cmp     [rdx+18h], eax
0x1800078de  ja      short loc_1800078B5
0x1800078e0  cmp     [rdx+28h], eax
0x1800078e3  ja      short loc_1800078B5
0x1800078e5  mov     ecx, r10d
0x1800078e8  jmp     short loc_1800078BA
0x1800078ea  mov     r8d, [rcx+8]
0x1800078ee  cmp     r8d, 0FFF7h
0x1800078f5  ja      short loc_1800078B5
0x1800078f7  movzx   eax, word ptr [rcx+4]
0x1800078fb  cmp     r8d, eax
0x1800078fe  jb      short loc_1800078B5
0x180007900  movzx   ecx, word ptr [rcx+18h]
0x180007904  mov     r9d, [rdx+14h]
0x180007908  add     r9d, ecx
0x18000790b  cmp     r9d, r8d
0x18000790e  ja      short loc_1800078B5
0x180007910  cmp     r9d, ecx
0x180007913  jb      short loc_1800078B5
0x180007915  movzx   ecx, word ptr [rdx+10h]
0x180007919  mov     r9d, [rdx+0Ch]
0x18000791d  add     r9d, ecx
0x180007920  cmp     r9d, ecx
0x180007923  jb      short loc_1800078B5
0x180007925  cmp     r9d, r8d
0x180007928  ja      short loc_1800078B5
0x18000792a  movzx   ecx, word ptr [rdx+2Ch]
0x18000792e  mov     r9d, [rdx+28h]
0x180007932  add     r9d, ecx
0x180007935  cmp     r9d, ecx
0x180007938  jb      loc_1800078B5
0x18000793e  cmp     r9d, r8d
0x180007941  ja      loc_1800078B5
0x180007947  movzx   ecx, word ptr [rdx+20h]
0x18000794b  mov     r9d, [rdx+1Ch]
0x18000794f  lea     eax, [rcx+r9]
0x180007953  cmp     eax, ecx
0x180007955  jb      loc_1800078B5
0x18000795b  cmp     eax, r8d
0x18000795e  ja      loc_1800078B5
0x180007964  test    r9d, r9d
0x180007967  jz      short loc_1800079E2
0x180007969  cmp     ecx, 1Ch
0x18000796c  jb      loc_1800078B5
0x180007972  mov     eax, [rdx+24h]
0x180007975  test    al, 10h
0x180007977  jnz     loc_1800078E5
0x18000797d  movzx   r8d, word ptr [r9+rdx+2]
0x180007983  cmp     r8d, ecx
0x180007986  ja      loc_1800078B5
0x18000798c  cmp     r8w, [r9+rdx]
0x180007991  jb      loc_1800078B5
0x180007997  cmp     word ptr [r9+rdx], 1Ch
0x18000799d  jb      loc_1800078B5
0x1800079a3  mov     ecx, [r9+rdx+14h]
0x1800079a8  movzx   edx, word ptr [r9+rdx+18h]
0x1800079ae  add     edx, ecx
0x1800079b0  cmp     edx, ecx
0x1800079b2  jb      loc_1800078B5
0x1800079b8  cmp     edx, r8d
0x1800079bb  jbe     loc_1800078E5
0x1800079c1  jmp     loc_1800078B5
0x1800079c6  cmp     dword ptr [rcx+4], 48h ; 'H'
0x1800079ca  jb      loc_1800078B5
0x1800079d0  cmp     [rcx+40h], eax
0x1800079d3  ja      loc_1800078B5
0x1800079d9  add     rdx, 8
0x1800079dd  jmp     loc_1800078D0
0x1800079e2  test    cx, cx
0x1800079e5  jz      loc_1800078E5
0x1800079eb  jmp     loc_1800078B5
```
