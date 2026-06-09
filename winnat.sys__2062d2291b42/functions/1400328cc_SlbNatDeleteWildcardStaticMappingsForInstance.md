# SlbNatDeleteWildcardStaticMappingsForInstance

- ea: `0x1400328cc`
- end: `0x140032984`
- name: `SlbNatDeleteWildcardStaticMappingsForInstance`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140032430`

## callees

- `0x140032228`
- `0x1400326d0`
- `0x1400328cc`

## pseudocode

```c
void __fastcall SlbNatDeleteWildcardStaticMappingsForInstance(__int64 a1)
{
  PVOID *v1; // rbx
  unsigned __int16 *v3; // rcx
  PVOID *v4; // rsi
  PVOID **v5; // rax
  PVOID *v6; // rdi
  PVOID *v7; // rax

  v1 = (PVOID *)qword_140027358;
  if ( qword_140027358 != &qword_140027358 )
  {
    do
    {
      v3 = (unsigned __int16 *)v1[2];
      if ( v3 != (unsigned __int16 *)(v1 + 2) )
      {
        do
        {
          v4 = *(PVOID **)v3;
          if ( *((_QWORD *)v3 + 16) == *(_QWORD *)(a1 + 288) )
          {
            if ( v4[1] != v3 )
              goto LABEL_15;
            v5 = (PVOID **)*((_QWORD *)v3 + 1);
            if ( *v5 != (PVOID *)v3 )
              goto LABEL_15;
            *v5 = v4;
            v4[1] = v5;
            --*((_DWORD *)v1 + 8);
            SlbNatDeleteStaticMapping(v3, a1);
          }
          v3 = (unsigned __int16 *)v4;
        }
        while ( v4 != v1 + 2 );
      }
      v6 = (PVOID *)*v1;
      if ( (*((_BYTE *)v1 + 92) & 1) != 0 && !*((_DWORD *)v1 + 8) )
      {
        if ( v6[1] != v1 || (v7 = (PVOID *)v1[1], *v7 != v1) )
LABEL_15:
          __fastfail(3u);
        *v7 = v6;
        v6[1] = v7;
        SlbNatDeleteExternalAddress((char *)v1, a1);
      }
      v1 = v6;
    }
    while ( v6 != &qword_140027358 );
  }
}

```

## disassembly

```asm
0x1400328cc  push    rbx
0x1400328ce  push    rbp
0x1400328cf  push    rsi
0x1400328d0  push    rdi
0x1400328d1  push    r14
0x1400328d3  sub     rsp, 20h
0x1400328d7  mov     rbx, cs:qword_140027358
0x1400328de  lea     r14, qword_140027358
0x1400328e5  mov     rbp, rcx
0x1400328e8  cmp     rbx, r14
0x1400328eb  jz      loc_140032971
0x1400328f1  lea     rdi, [rbx+10h]
0x1400328f5  mov     rcx, [rdi]; P
0x1400328f8  cmp     rcx, rdi
0x1400328fb  jz      short loc_140032939
0x1400328fd  mov     rax, [rbp+120h]
0x140032904  mov     rsi, [rcx]
0x140032907  cmp     [rcx+80h], rax
0x14003290e  jnz     short loc_140032931
0x140032910  cmp     [rsi+8], rcx
0x140032914  jnz     short loc_14003297D
0x140032916  mov     rax, [rcx+8]
0x14003291a  cmp     [rax], rcx
0x14003291d  jnz     short loc_14003297D
0x14003291f  mov     [rax], rsi
0x140032922  mov     rdx, rbp
0x140032925  mov     [rsi+8], rax
0x140032929  dec     dword ptr [rbx+20h]
0x14003292c  call    SlbNatDeleteStaticMapping
0x140032931  mov     rcx, rsi
0x140032934  cmp     rsi, rdi
0x140032937  jnz     short loc_1400328FD
0x140032939  test    byte ptr [rbx+5Ch], 1
0x14003293d  mov     rdi, [rbx]
0x140032940  jz      short loc_140032969
0x140032942  cmp     dword ptr [rbx+20h], 0
0x140032946  jnz     short loc_140032969
0x140032948  cmp     [rdi+8], rbx
0x14003294c  jnz     short loc_14003297D
0x14003294e  mov     rax, [rbx+8]
0x140032952  cmp     [rax], rbx
0x140032955  jnz     short loc_14003297D
0x140032957  mov     [rax], rdi
0x14003295a  mov     rdx, rbp
0x14003295d  mov     rcx, rbx; P
0x140032960  mov     [rdi+8], rax
0x140032964  call    SlbNatDeleteExternalAddress
0x140032969  mov     rbx, rdi
0x14003296c  cmp     rdi, r14
0x14003296f  jnz     short loc_1400328F1
0x140032971  add     rsp, 20h
0x140032975  pop     r14
0x140032977  pop     rdi
0x140032978  pop     rsi
0x140032979  pop     rbp
0x14003297a  pop     rbx
0x14003297b  retn
0x14003297d  mov     ecx, 3
0x140032982  int     29h; Win8: RtlFailFast(ecx)
```
