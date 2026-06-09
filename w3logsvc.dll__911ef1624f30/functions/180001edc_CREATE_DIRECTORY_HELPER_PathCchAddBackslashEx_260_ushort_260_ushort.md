# CREATE_DIRECTORY_HELPER::PathCchAddBackslashEx<260>(ushort (&)[260],ushort * *)

- ea: `0x180001edc`
- end: `0x180002002`
- name: `??$PathCchAddBackslashEx@$0BAE@@CREATE_DIRECTORY_HELPER@@CAJAEAY0BAE@GPEAPEAG@Z`
- size: `294`
- prototype: `__int64 __fastcall(_WORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180003078`

## callees

- `0x180001edc`

## pseudocode

```c
__int64 __fastcall CREATE_DIRECTORY_HELPER::PathCchAddBackslashEx<260>(_WORD *a1, _QWORD *a2)
{
  _WORD *v4; // rax
  __int64 v5; // r10
  unsigned int v6; // edx
  unsigned int v7; // r9d
  unsigned __int64 v8; // r11
  _WORD *v10; // r9
  unsigned __int64 v11; // r8
  __int64 v12; // rcx
  const wchar_t *v13; // rdx
  _WORD *v14; // rax
  __int64 v15; // r10
  _WORD *v16; // rcx
  __int64 v17; // rax

  *a2 = 0;
  if ( a1 )
  {
    v4 = a1;
    v5 = 260;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = -2147024809;
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (260 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      if ( v8 >= 0x104 )
        return 2147942522LL;
      v10 = &a1[v8];
      if ( !v8 || *(v10 - 1) == 92 )
      {
        v6 = 1;
      }
      else
      {
        v11 = 260 - v8;
        if ( 260 != v8 )
        {
          if ( v11 > 0x7FFFFFFF )
          {
            *v10 = 0;
          }
          else
          {
            v12 = 2147483646;
            v13 = L"\\";
            v14 = &a1[v8];
            v15 = 0;
            do
            {
              if ( !v12 )
                break;
              if ( !*v13 )
                break;
              *v14++ = *v13++;
              --v12;
              ++v15;
              --v11;
            }
            while ( v11 );
            v16 = v14 - 1;
            if ( v11 )
              v16 = v14;
            v17 = v15 - 1;
            *v16 = 0;
            v6 = v11 == 0 ? 0x8007007A : 0;
            if ( v11 )
              v17 = v15;
            v10 += v17;
          }
        }
        if ( (v6 & 0x80000000) != 0 )
          return v6;
      }
      *a2 = v10;
      return v6;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v7;
}

```

## disassembly

```asm
0x180001edc  push    rbx
0x180001ede  push    rsi
0x180001edf  push    rdi
0x180001ee0  xor     esi, esi
0x180001ee2  mov     rdi, rdx
0x180001ee5  mov     [rdx], rsi
0x180001ee8  mov     rbx, rcx
0x180001eeb  test    rcx, rcx
0x180001eee  jz      loc_180001FF5
0x180001ef4  mov     r8d, 104h
0x180001efa  mov     rax, rcx
0x180001efd  mov     r10d, r8d
0x180001f00  cmp     [rax], si
0x180001f03  jz      short loc_180001F0F
0x180001f05  add     rax, 2
0x180001f09  sub     r10, 1
0x180001f0d  jnz     short loc_180001F00
0x180001f0f  mov     rax, r10
0x180001f12  mov     edx, 80070057h
0x180001f17  neg     rax
0x180001f1a  mov     rcx, r8
0x180001f1d  mov     rax, r10
0x180001f20  sbb     r9d, r9d
0x180001f23  sub     rcx, r10
0x180001f26  not     r9d
0x180001f29  and     r9d, edx
0x180001f2c  neg     rax
0x180001f2f  sbb     r11, r11
0x180001f32  and     r11, rcx
0x180001f35  test    r10, r10
0x180001f38  jz      loc_180001FFB
0x180001f3e  cmp     r11, r8
0x180001f41  jb      short loc_180001F4B
0x180001f43  lea     eax, [rdx+23h]
0x180001f46  jmp     loc_180001FFE
0x180001f4b  lea     r9, [rbx+r11*2]
0x180001f4f  test    r11, r11
0x180001f52  jz      loc_180001FE9
0x180001f58  cmp     word ptr [r9-2], 5Ch ; '\'
0x180001f5e  jz      loc_180001FE9
0x180001f64  sub     r8, r11
0x180001f67  jz      short loc_180001FDA
0x180001f69  cmp     r8, 7FFFFFFFh
0x180001f70  ja      short loc_180001FDF
0x180001f72  mov     ecx, 7FFFFFFEh
0x180001f77  lea     rdx, asc_180011C30; "\\"
0x180001f7e  mov     rax, r9
0x180001f81  mov     r10, rsi
0x180001f84  test    rcx, rcx
0x180001f87  jz      short loc_180001FAB
0x180001f89  movzx   r11d, word ptr [rdx]
0x180001f8d  test    r11w, r11w
0x180001f91  jz      short loc_180001FAB
0x180001f93  mov     [rax], r11w
0x180001f97  add     rdx, 2
0x180001f9b  add     rax, 2
0x180001f9f  dec     rcx
0x180001fa2  inc     r10
0x180001fa5  sub     r8, 1
0x180001fa9  jnz     short loc_180001F84
0x180001fab  lea     rcx, [rax-2]
0x180001faf  test    r8, r8
0x180001fb2  cmovnz  rcx, rax
0x180001fb6  mov     rax, r8
0x180001fb9  neg     rax
0x180001fbc  lea     rax, [r10-1]
0x180001fc0  sbb     edx, edx
0x180001fc2  not     edx
0x180001fc4  mov     [rcx], si
0x180001fc7  and     edx, 8007007Ah
0x180001fcd  test    r8, r8
0x180001fd0  cmovnz  rax, r10
0x180001fd4  lea     r9, [r9+rax*2]
0x180001fd8  jmp     short loc_180001FE3
0x180001fda  test    r8, r8
0x180001fdd  jz      short loc_180001FE3
0x180001fdf  mov     [r9], si
0x180001fe3  test    edx, edx
0x180001fe5  js      short loc_180001FF1
0x180001fe7  jmp     short loc_180001FEE
0x180001fe9  mov     edx, 1
0x180001fee  mov     [rdi], r9
0x180001ff1  mov     eax, edx
0x180001ff3  jmp     short loc_180001FFE
0x180001ff5  mov     r9d, 80070057h
0x180001ffb  mov     eax, r9d
0x180001ffe  pop     rdi
0x180001fff  pop     rsi
0x180002000  pop     rbx
0x180002001  retn
```
