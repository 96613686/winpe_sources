# CNTFSSecurity::FixSynchronizeAccess(ulong,void *)

- ea: `0x180006ce8`
- end: `0x180006d9d`
- name: `?FixSynchronizeAccess@CNTFSSecurity@@IEAAXKPEAX@Z`
- size: `181`
- prototype: `void __fastcall(CNTFSSecurity *this, char, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007950`

## callees

- `0x180006ce8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180006d2f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180006d2f`

## pseudocode

```c
void __fastcall CNTFSSecurity::FixSynchronizeAccess(CNTFSSecurity *this, char a2, void *a3)
{
  PACL v3; // rdx
  int v4; // r8d
  PACL v5; // rcx
  BYTE AclRevision; // al
  int v7; // eax
  CNTFSSecurity *v8; // [rsp+30h] [rbp+8h] BYREF
  WINBOOL v9; // [rsp+40h] [rbp+18h] BYREF
  PACL v10; // [rsp+48h] [rbp+20h] BYREF

  if ( a3 )
  {
    v8 = this;
    if ( (a2 & 4) != 0 )
    {
      v9 = 0;
      LODWORD(v8) = 0;
      v10 = 0;
      GetSecurityDescriptorDacl(a3, &v9, &v10, (LPBOOL)&v8);
      v3 = v10;
      if ( v10 )
      {
        v4 = 0;
        v5 = v10 + 1;
        if ( v10->AceCount )
        {
          while ( 1 )
          {
            AclRevision = v5->AclRevision;
            if ( v5->AclRevision )
            {
              if ( AclRevision != 9 )
                break;
            }
            v7 = *(_DWORD *)&v5->AceCount;
            if ( v7 )
            {
              *(_DWORD *)&v5->AceCount = v7 | 0x100000;
LABEL_13:
              v3 = v10;
            }
LABEL_14:
            ++v4;
            v5 = (PACL)((char *)v5 + v5->AclSize);
            if ( v4 >= v3->AceCount )
              return;
          }
          if ( AclRevision != 1 && AclRevision != 10 || *(_DWORD *)&v5->AceCount != 983551 )
            goto LABEL_14;
          *(_DWORD *)&v5->AceCount = 2032127;
          goto LABEL_13;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180006ce8  test    r8, r8
0x180006ceb  jz      locret_180006D9C
0x180006cf1  mov     r11, rsp
0x180006cf4  mov     [r11+8], rcx
0x180006cf8  sub     rsp, 28h
0x180006cfc  mov     rax, r8
0x180006cff  test    dl, 4
0x180006d02  jz      loc_180006D98
0x180006d08  lea     r9, [r11+8]; lpbDaclDefaulted
0x180006d0c  mov     [rsp+28h+arg_10], 0
0x180006d14  lea     r8, [r11+20h]; pDacl
0x180006d18  mov     dword ptr [rsp+28h+arg_0], 0
0x180006d20  lea     rdx, [r11+18h]; lpbDaclPresent
0x180006d24  mov     qword ptr [r11+20h], 0
0x180006d2c  mov     rcx, rax; pSecurityDescriptor
0x180006d2f  call    cs:__imp_GetSecurityDescriptorDacl
0x180006d35  mov     rdx, [rsp+28h+arg_18]
0x180006d3a  test    rdx, rdx
0x180006d3d  jz      short loc_180006D98
0x180006d3f  xor     r8d, r8d
0x180006d42  lea     rcx, [rdx+8]
0x180006d46  xor     eax, eax
0x180006d48  cmp     ax, [rdx+4]
0x180006d4c  jnb     short loc_180006D98
0x180006d4e  mov     al, [rcx]
0x180006d50  test    al, al
0x180006d52  jz      short loc_180006D72
0x180006d54  cmp     al, 9
0x180006d56  jz      short loc_180006D72
0x180006d58  cmp     al, 1
0x180006d5a  jz      short loc_180006D60
0x180006d5c  cmp     al, 0Ah
0x180006d5e  jnz     short loc_180006D85
0x180006d60  cmp     dword ptr [rcx+4], 0F01FFh
0x180006d67  jnz     short loc_180006D85
0x180006d69  mov     dword ptr [rcx+4], 1F01FFh
0x180006d70  jmp     short loc_180006D80
0x180006d72  mov     eax, [rcx+4]
0x180006d75  test    eax, eax
0x180006d77  jz      short loc_180006D85
0x180006d79  bts     eax, 14h
0x180006d7d  mov     [rcx+4], eax
0x180006d80  mov     rdx, [rsp+28h+arg_18]
0x180006d85  movzx   eax, word ptr [rcx+2]
0x180006d89  inc     r8d
0x180006d8c  add     rcx, rax
0x180006d8f  movzx   eax, word ptr [rdx+4]
0x180006d93  cmp     r8d, eax
0x180006d96  jl      short loc_180006D4E
0x180006d98  add     rsp, 28h
0x180006d9c  retn
```
