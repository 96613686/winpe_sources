# SdpParseResourceDescriptor(ushort *,ushort * *,ulong *)

- ea: `0x180006620`
- end: `0x1800066ef`
- name: `?SdpParseResourceDescriptor@@YAJPEAGPEAPEAGPEAK@Z`
- size: `207`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000615c`

## callees

- `0x180006620`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800066c9`
- `msvcrt!_wtoi` at `0x1800066c9`

## string_xrefs

- `0x180006643`: `SdpParseResourceDescriptor`

## pseudocode

```c
__int64 __fastcall SdpParseResourceDescriptor(unsigned __int16 *a1, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  unsigned int v6; // r8d
  unsigned __int16 *v7; // rdi
  unsigned __int16 v8; // ax
  unsigned __int16 *v9; // rcx
  int v10; // eax

  v3 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( *a1 == 64 )
        {
          v7 = a1 + 1;
          v8 = a1[1];
          v9 = a1 + 1;
          while ( v8 && v8 != 44 )
            v8 = *++v9;
          if ( *v9 == 44 )
          {
            *v9 = 0;
            if ( v9[1] == 45 )
            {
              v10 = _wtoi(v9 + 2);
              if ( v10 )
              {
                *a2 = v7;
                *a3 = v10;
                return v3;
              }
              v6 = 377;
            }
            else
            {
              v6 = 368;
            }
          }
          else
          {
            v6 = 361;
          }
        }
        else
        {
          v6 = 348;
        }
      }
      else
      {
        v6 = 342;
      }
    }
    else
    {
      v6 = 341;
    }
  }
  else
  {
    v6 = 340;
  }
  v3 = -2147024809;
  SdpDebugTrace(1u, L"SdpParseResourceDescriptor", v6, -2147024809);
  return v3;
}

```

## disassembly

```asm
0x180006620  push    rbx
0x180006622  push    rsi
0x180006623  push    rdi
0x180006624  push    r14
0x180006626  sub     rsp, 28h
0x18000662a  xor     ebx, ebx
0x18000662c  mov     rsi, r8
0x18000662f  mov     r14, rdx
0x180006632  test    rcx, rcx
0x180006635  jnz     short loc_18000665C
0x180006637  mov     r8d, 154h; int
0x18000663d  mov     r9d, 80070057h; int
0x180006643  lea     rdx, aSdpparseresour; "SdpParseResourceDescriptor"
0x18000664a  mov     ecx, 1; Level
0x18000664f  mov     ebx, r9d
0x180006652  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006657  jmp     loc_1800066E3
0x18000665c  test    r14, r14
0x18000665f  jnz     short loc_180006669
0x180006661  mov     r8d, 155h
0x180006667  jmp     short loc_18000663D
0x180006669  test    rsi, rsi
0x18000666c  jnz     short loc_180006676
0x18000666e  mov     r8d, 156h
0x180006674  jmp     short loc_18000663D
0x180006676  cmp     word ptr [rcx], 40h ; '@'
0x18000667a  jz      short loc_180006684
0x18000667c  mov     r8d, 15Ch
0x180006682  jmp     short loc_18000663D
0x180006684  lea     rdi, [rcx+2]
0x180006688  movzx   eax, word ptr [rdi]
0x18000668b  mov     rcx, rdi
0x18000668e  jmp     short loc_18000669D
0x180006690  cmp     ax, 2Ch ; ','
0x180006694  jz      short loc_1800066A2
0x180006696  add     rcx, 2
0x18000669a  movzx   eax, word ptr [rcx]
0x18000669d  test    ax, ax
0x1800066a0  jnz     short loc_180006690
0x1800066a2  cmp     word ptr [rcx], 2Ch ; ','
0x1800066a6  jz      short loc_1800066B0
0x1800066a8  mov     r8d, 169h
0x1800066ae  jmp     short loc_18000663D
0x1800066b0  mov     [rcx], bx
0x1800066b3  cmp     word ptr [rcx+2], 2Dh ; '-'
0x1800066b8  jz      short loc_1800066C5
0x1800066ba  mov     r8d, 170h
0x1800066c0  jmp     loc_18000663D
0x1800066c5  add     rcx, 4; String
0x1800066c9  call    cs:__imp__wtoi
0x1800066cf  test    eax, eax
0x1800066d1  jnz     short loc_1800066DE
0x1800066d3  mov     r8d, 179h
0x1800066d9  jmp     loc_18000663D
0x1800066de  mov     [r14], rdi
0x1800066e1  mov     [rsi], eax
0x1800066e3  mov     eax, ebx
0x1800066e5  add     rsp, 28h
0x1800066e9  pop     r14
0x1800066eb  pop     rdi
0x1800066ec  pop     rsi
0x1800066ed  pop     rbx
0x1800066ee  retn
```
