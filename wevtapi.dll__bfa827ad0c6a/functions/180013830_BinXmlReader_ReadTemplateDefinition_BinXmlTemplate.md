# BinXmlReader::ReadTemplateDefinition(BinXmlTemplate &)

- ea: `0x180013830`
- end: `0x18001398e`
- name: `?ReadTemplateDefinition@BinXmlReader@@QEAAXAEAVBinXmlTemplate@@@Z`
- size: `350`
- prototype: `void __fastcall(BinXmlReader *__hidden this, struct BinXmlTemplate *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180005ad4`
- `0x18002fdb4`

## callees

- `0x1800130b0`
- `0x180013830`
- `0x1800231d0`
- `0x180023548`
- `0x180038fa4`
- `0x18003c010`

## pseudocode

```c
void __fastcall BinXmlReader::ReadTemplateDefinition(BinXmlReader *this, struct BinXmlTemplate *a2)
{
  __int64 v2; // r10
  __int64 v5; // r11
  char v6; // r9
  __int64 *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // edx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v14; // [rsp+30h] [rbp-28h]
  int v15; // [rsp+38h] [rbp-20h]
  int v16; // [rsp+3Ch] [rbp-1Ch]
  int v17; // [rsp+40h] [rbp-18h]
  int v18; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 2);
  v5 = *(unsigned int *)(v2 + 8);
  if ( (unsigned int)v5 >= *(_DWORD *)(v2 + 12) )
    goto LABEL_10;
  v6 = *(_BYTE *)(v5 + *(_QWORD *)v2);
  *(_DWORD *)(v2 + 8) = v5 + 1;
  if ( !v6 )
  {
    v7 = (__int64 *)*((_QWORD *)this + 2);
    if ( *v7 )
    {
      v8 = *((unsigned int *)v7 + 2);
      if ( (unsigned int)(*((_DWORD *)v7 + 3) - v8) >= 0x10 )
      {
        *((_OWORD *)a2 + 1) = *(_OWORD *)(v8 + *v7);
        *((_DWORD *)v7 + 2) += 16;
        v9 = *((unsigned int *)v7 + 2);
        if ( (unsigned int)(*((_DWORD *)v7 + 3) - v9) >= 4 )
        {
          v10 = *v7;
          v11 = *(unsigned int *)(v9 + *v7);
          *((_DWORD *)v7 + 2) = v9 + 4;
          *(_QWORD *)a2 = v10 + (unsigned int)(v9 + 4);
          *((_QWORD *)a2 + 1) = v11;
          if ( *v7 )
          {
            if ( (unsigned int)v11 <= 0x10000000 )
            {
              v12 = *((_DWORD *)v7 + 2);
              if ( (unsigned int)v11 <= *((_DWORD *)v7 + 3) - v12 )
              {
                *((_DWORD *)v7 + 2) = v11 + v12;
                return;
              }
            }
          }
        }
      }
    }
LABEL_10:
    UserBuffer::ThrowUnexpectedEOFException();
  }
  if ( !*((_QWORD *)this + 12) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
    }
    v15 = 13;
    v16 = -1;
    v14 = 0;
    v17 = 1399;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  UserBuffer::Read4(*((UserBuffer **)this + 2), &v18);
  (***((void (__fastcall ****)(_QWORD, _QWORD, struct BinXmlTemplate *))this + 12))(
    *((_QWORD *)this + 12),
    *((_QWORD *)this + 2),
    a2);
}

```

## disassembly

```asm
0x180013830  mov     [rsp+arg_8], rbx
0x180013835  push    rdi
0x180013836  sub     rsp, 50h
0x18001383a  mov     r10, [rcx+10h]
0x18001383e  mov     rdi, rdx
0x180013841  mov     rbx, rcx
0x180013844  mov     r11d, [r10+8]
0x180013848  cmp     r11d, [r10+0Ch]
0x18001384c  jnb     loc_1800138E7
0x180013852  mov     rax, [r10]
0x180013855  movzx   r9d, byte ptr [r11+rax]
0x18001385a  lea     eax, [r11+1]
0x18001385e  mov     [r10+8], eax
0x180013862  test    r9b, r9b
0x180013865  jnz     loc_1800138ED
0x18001386b  mov     rax, [rcx+10h]
0x18001386f  mov     rdx, [rax]
0x180013872  test    rdx, rdx
0x180013875  jz      short loc_1800138E7
0x180013877  mov     r8d, [rax+8]
0x18001387b  mov     ecx, [rax+0Ch]
0x18001387e  sub     ecx, r8d
0x180013881  cmp     ecx, 10h
0x180013884  jb      short loc_1800138E7
0x180013886  movups  xmm0, xmmword ptr [r8+rdx]
0x18001388b  movups  xmmword ptr [rdi+10h], xmm0
0x18001388f  add     dword ptr [rax+8], 10h
0x180013893  mov     edx, [rax+8]
0x180013896  mov     ecx, [rax+0Ch]
0x180013899  sub     ecx, edx
0x18001389b  cmp     ecx, 4
0x18001389e  jb      short loc_1800138E7
0x1800138a0  mov     r8, [rax]
0x1800138a3  lea     ecx, [rdx+4]
0x1800138a6  mov     r9d, [rdx+r8]
0x1800138aa  mov     [rax+8], ecx
0x1800138ad  mov     edx, ecx
0x1800138af  add     rdx, r8
0x1800138b2  mov     [rdi], rdx
0x1800138b5  mov     [rdi+8], r9
0x1800138b9  cmp     qword ptr [rax], 0
0x1800138bd  jz      short loc_1800138E7
0x1800138bf  cmp     r9d, 10000000h
0x1800138c6  ja      short loc_1800138E7
0x1800138c8  mov     ecx, [rax+0Ch]
0x1800138cb  mov     edx, [rax+8]
0x1800138ce  sub     ecx, edx
0x1800138d0  cmp     r9d, ecx
0x1800138d3  ja      short loc_1800138E7
0x1800138d5  lea     ecx, [r9+rdx]
0x1800138d9  mov     [rax+8], ecx
0x1800138dc  mov     rbx, [rsp+58h+arg_8]
0x1800138e1  add     rsp, 50h
0x1800138e5  pop     rdi
0x1800138e6  retn
0x1800138e7  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x1800138ed  cmp     qword ptr [rcx+60h], 0
0x1800138f2  jz      short loc_18001391A
0x1800138f4  mov     rcx, [rcx+10h]; this
0x1800138f8  lea     rdx, [rsp+58h+arg_0]; void *
0x1800138fd  call    ?Read4@UserBuffer@@QEAAXPEAX@Z; UserBuffer::Read4(void *)
0x180013902  mov     rcx, [rbx+60h]
0x180013906  mov     r8, rdi
0x180013909  mov     rdx, [rbx+10h]
0x18001390d  mov     rax, [rcx]
0x180013910  mov     rax, [rax]
0x180013913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013918  jmp     short loc_1800138DC
0x18001391a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013921  lea     rax, WPP_GLOBAL_Control
0x180013928  cmp     rcx, rax
0x18001392b  jz      short loc_180013954
0x18001392d  test    byte ptr [rcx+1Ch], 2
0x180013931  jz      short loc_180013954
0x180013933  cmp     byte ptr [rcx+19h], 2
0x180013937  jb      short loc_180013954
0x180013939  mov     rcx, [rcx+10h]
0x18001393d  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180013944  mov     edx, 24h ; '$'
0x180013949  mov     r9d, 0Dh
0x18001394f  call    WPP_SF_D
0x180013954  xorps   xmm0, xmm0
0x180013957  mov     [rsp+58h+var_20], 0Dh
0x18001395f  xor     eax, eax
0x180013961  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x180013969  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180013970  mov     [rsp+58h+var_28], rax
0x180013975  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001397a  mov     [rsp+58h+var_18], 577h
0x180013982  movdqu  [rsp+58h+pExceptionObject], xmm0
0x180013988  call    _CxxThrowException_0
```
