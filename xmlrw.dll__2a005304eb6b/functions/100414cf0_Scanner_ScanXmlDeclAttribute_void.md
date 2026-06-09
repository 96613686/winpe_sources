# Scanner::ScanXmlDeclAttribute(void)

- ea: `0x100414cf0`
- end: `0x100414f6f`
- name: `?ScanXmlDeclAttribute@Scanner@@AEAAXXZ`
- size: `639`
- prototype: `void __fastcall(Scanner *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x100401780`
- `0x100414cf0`
- `0x100439df0`

## pseudocode

```c
void __fastcall Scanner::ScanXmlDeclAttribute(Scanner *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int16 v5; // ax
  __int64 v6; // rcx
  __int16 v7; // ax
  __int64 v8; // rax
  __int16 v9; // ax

  if ( *((_DWORD *)this + 18) != 1 )
    *((_WORD *)this + 92) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
  switch ( *((_WORD *)this + 92) )
  {
    case 9:
    case 0x20:
      goto LABEL_8;
    case 0xA:
LABEL_4:
      v2 = *((_QWORD *)this + 8);
      ++*(_DWORD *)(v2 + 104);
      goto LABEL_7;
    case 0xD:
LABEL_5:
      v3 = *((_QWORD *)this + 8);
      *(_QWORD *)(v3 + 96) = *(_QWORD *)(v3 + 48);
      ++*(_DWORD *)(v3 + 104);
      v4 = *((_QWORD *)this + 8);
      *(_QWORD *)(v4 + 56) = *(_QWORD *)(v4 + 48);
      *(_DWORD *)(v4 + 88) = 1;
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
      *((_WORD *)this + 92) = v5;
      if ( v5 != 10 )
        goto LABEL_9;
      v2 = *((_QWORD *)this + 8);
LABEL_7:
      *(_QWORD *)(v2 + 96) = *(_QWORD *)(v2 + 48);
LABEL_8:
      while ( 2 )
      {
        v6 = *((_QWORD *)this + 8);
        *(_QWORD *)(v6 + 56) = *(_QWORD *)(v6 + 48);
        *(_DWORD *)(v6 + 88) = 1;
        v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
        *((_WORD *)this + 92) = v5;
LABEL_9:
        switch ( v5 )
        {
          case 9:
          case 32:
            continue;
          case 10:
            goto LABEL_4;
          case 13:
            goto LABEL_5;
          case 62:
            goto LABEL_17;
          case 63:
            v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
            *((_WORD *)this + 92) = v7;
            if ( v7 == 62 )
              goto LABEL_11;
            goto LABEL_18;
          default:
            (*((void (__fastcall **)(Scanner *))this + 36))(this);
            *((_QWORD *)this + 22) = Scanner::ScanAttributeEqual;
            *((_DWORD *)this + 18) = 12;
            return;
        }
      }
    case 0x3E:
LABEL_17:
      MXRRaiseException(-1072894388);
      __debugbreak();
    case 0x3F:
      v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
      *((_WORD *)this + 92) = v9;
      if ( v9 != 62 )
      {
LABEL_18:
        MXRRaiseException(-1072894429);
        __debugbreak();
      }
LABEL_11:
      *((_DWORD *)this + 18) = 2;
      --*((_DWORD *)this + 26);
      v8 = *((_QWORD *)this + 8);
      *((_QWORD *)this + 22) = *(_QWORD *)(*((_QWORD *)this + 12) + 8LL * (unsigned int)(*((_DWORD *)this + 26) - 1));
      *(_BYTE *)(v8 + 25) = 0;
      return;
    default:
      if ( !*(_BYTE *)(*((_QWORD *)this + 8) + 24LL) )
      {
        MXRRaiseException(-1072894431);
        __debugbreak();
      }
      MXRRaiseException(-1072894463);
      __debugbreak();
  }
}

```

## disassembly

```asm
0x100414cf0  push    rbx
0x100414cf2  sub     rsp, 20h
0x100414cf6  cmp     dword ptr [rcx+48h], 1
0x100414cfa  mov     rbx, rcx
0x100414cfd  jz      short loc_100414D17
0x100414cff  mov     rcx, [rcx+40h]
0x100414d03  mov     rax, [rcx]
0x100414d06  mov     rax, [rax+58h]
0x100414d0a  call    cs:__guard_dispatch_icall_fptr
0x100414d10  mov     [rbx+0B8h], ax
0x100414d17  movzx   eax, word ptr [rbx+0B8h]
0x100414d1e  add     eax, 0FFFFFFF7h; switch 55 cases
0x100414d21  mov     [rsp+28h+arg_0], rdi
0x100414d26  cmp     eax, 36h
0x100414d29  ja      def_100414D4A; jumptable 0000000100414D4A default case, cases 11,12,14-31,33-61
0x100414d2f  lea     rdi, __ImageBase
0x100414d36  cdqe
0x100414d38  movzx   eax, ds:(byte_100414EE8 - 100400000h)[rdi+rax]
0x100414d40  mov     ecx, ds:(jpt_100414D4A - 100400000h)[rdi+rax*4]
0x100414d47  add     rcx, rdi
0x100414d4a  jmp     rcx; switch jump
0x100414d4c  mov     rcx, [rbx+40h]; jumptable 0000000100414D4A case 10
0x100414d50  inc     dword ptr [rcx+68h]
0x100414d53  jmp     short loc_100414D99
0x100414d55  mov     rcx, [rbx+40h]; jumptable 0000000100414D4A case 13
0x100414d59  mov     rax, [rcx+30h]
0x100414d5d  mov     [rcx+60h], rax
0x100414d61  inc     dword ptr [rcx+68h]
0x100414d64  mov     rcx, [rbx+40h]
0x100414d68  mov     rax, [rcx+30h]
0x100414d6c  mov     [rcx+38h], rax
0x100414d70  mov     dword ptr [rcx+58h], 1
0x100414d77  mov     rcx, [rbx+40h]
0x100414d7b  mov     rax, [rcx]
0x100414d7e  mov     rax, [rax+58h]
0x100414d82  call    cs:__guard_dispatch_icall_fptr
0x100414d88  mov     [rbx+0B8h], ax
0x100414d8f  cmp     ax, 0Ah
0x100414d93  jnz     short loc_100414DD0
0x100414d95  mov     rcx, [rbx+40h]
0x100414d99  mov     rax, [rcx+30h]
0x100414d9d  mov     [rcx+60h], rax
0x100414da1  mov     rcx, [rbx+40h]; jumptable 0000000100414D4A cases 9,32
0x100414da5  mov     rax, [rcx+30h]
0x100414da9  mov     [rcx+38h], rax
0x100414dad  mov     dword ptr [rcx+58h], 1
0x100414db4  mov     rcx, [rbx+40h]
0x100414db8  mov     rax, [rcx]
0x100414dbb  mov     rax, [rax+58h]
0x100414dbf  call    cs:__guard_dispatch_icall_fptr
0x100414dc5  mov     [rbx+0B8h], ax
0x100414dcc  nop     dword ptr [rax+00h]
0x100414dd0  movzx   eax, ax
0x100414dd3  add     eax, 0FFFFFFF7h; switch 55 cases
0x100414dd6  cmp     eax, 36h
0x100414dd9  ja      short def_100414DEF; jumptable 0000000100414DEF default case, cases 11,12,14-31,33-61
0x100414ddb  cdqe
0x100414ddd  movzx   eax, ds:(byte_100414F38 - 100400000h)[rdi+rax]
0x100414de5  mov     ecx, ds:(jpt_100414DEF - 100400000h)[rdi+rax*4]
0x100414dec  add     rcx, rdi
0x100414def  jmp     rcx; switch jump
0x100414df1  mov     rcx, [rbx+40h]; jumptable 0000000100414DEF case 63
0x100414df5  mov     rax, [rcx]
0x100414df8  mov     rax, [rax+58h]
0x100414dfc  call    cs:__guard_dispatch_icall_fptr
0x100414e02  mov     [rbx+0B8h], ax
0x100414e09  cmp     ax, 3Eh ; '>'
0x100414e0d  jnz     loc_100414EB7
0x100414e13  mov     dword ptr [rbx+48h], 2
0x100414e1a  dec     dword ptr [rbx+68h]
0x100414e1d  mov     ecx, [rbx+68h]
0x100414e20  mov     rax, [rbx+60h]
0x100414e24  dec     ecx
0x100414e26  mov     rcx, [rax+rcx*8]
0x100414e2a  mov     rax, [rbx+40h]
0x100414e2e  mov     [rbx+0B0h], rcx
0x100414e35  mov     byte ptr [rax+19h], 0
0x100414e39  mov     rdi, [rsp+28h+arg_0]
0x100414e3e  add     rsp, 20h
0x100414e42  pop     rbx
0x100414e43  retn
0x100414e44  mov     rax, [rbx+120h]; jumptable 0000000100414DEF default case, cases 11,12,14-31,33-61
0x100414e4b  mov     rcx, rbx
0x100414e4e  call    cs:__guard_dispatch_icall_fptr
0x100414e54  mov     rdi, [rsp+28h+arg_0]
0x100414e59  lea     rax, ?ScanAttributeEqual@Scanner@@AEAAXXZ; Scanner::ScanAttributeEqual(void)
0x100414e60  mov     [rbx+0B0h], rax
0x100414e67  mov     dword ptr [rbx+48h], 0Ch
0x100414e6e  add     rsp, 20h
0x100414e72  pop     rbx
0x100414e73  retn
0x100414e74  mov     rcx, [rbx+40h]; jumptable 0000000100414D4A case 63
0x100414e78  mov     rax, [rcx]
0x100414e7b  mov     rax, [rax+58h]
0x100414e7f  call    cs:__guard_dispatch_icall_fptr
0x100414e85  mov     [rbx+0B8h], ax
0x100414e8c  cmp     ax, 3Eh ; '>'
0x100414e90  jnz     short loc_100414EB7
0x100414e92  jmp     loc_100414E13
0x100414e97  mov     rax, [rbx+40h]; jumptable 0000000100414D4A default case, cases 11,12,14-31,33-61
0x100414e9b  cmp     byte ptr [rax+18h], 0
0x100414e9f  jnz     short loc_100414EC2
0x100414ea1  mov     ecx, 0C00CEE21h; int
0x100414ea6  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100414eab  int     3; Trap to Debugger
0x100414eac  mov     ecx, 0C00CEE4Ch; jumptable 0000000100414D4A case 62
0x100414eb1  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100414eb6  int     3; Trap to Debugger
0x100414eb7  mov     ecx, 0C00CEE23h; int
0x100414ebc  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100414ec1  int     3; Trap to Debugger
0x100414ec2  mov     ecx, 0C00CEE01h; int
0x100414ec7  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100414ecc  int     3; Trap to Debugger
```
