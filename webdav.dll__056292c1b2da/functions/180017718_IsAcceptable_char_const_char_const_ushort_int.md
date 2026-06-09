# IsAcceptable(char const *,char const *,ushort,int *)

- ea: `0x180017718`
- end: `0x180017a3e`
- name: `?IsAcceptable@@YAJPEBD0GPEAH@Z`
- size: `806`
- prototype: `__int64 __fastcall(const char *, const char *Str, unsigned __int16, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180016708`

## callees

- `0x1800174f8`
- `0x180017718`
- `0x180022520`

## import_xrefs

- `msvcrt!_stricmp` at `0x180017943`
- `msvcrt!_stricmp` at `0x18001795f`
- `msvcrt!_stricmp` at `0x180017943`
- `msvcrt!_stricmp` at `0x18001795f`
- `msvcrt!strstr` at `0x180017783`
- `msvcrt!strstr` at `0x180017783`
- `msvcrt!strchr` at `0x180017847`
- `msvcrt!strchr` at `0x1800178c6`
- `msvcrt!strchr` at `0x180017847`
- `msvcrt!strchr` at `0x1800178c6`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800178ac`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800178ac`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18001785d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18001785d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001786e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017878`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017883`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001788f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017899`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001798c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017996`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179a1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179b7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179c1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179cc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179d6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179e0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179f0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179fa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017a05`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017a0f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017a19`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001786e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017878`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017883`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001788f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017899`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001798c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017996`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179a1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179b7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179c1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179cc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179d6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179e0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179f0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800179fa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017a05`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017a0f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180017a19`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800177ac`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800177bd`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180017810`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180017824`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180017839`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800177ac`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800177bd`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180017810`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180017824`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180017839`

## pseudocode

```c
__int64 __fastcall IsAcceptable(const char *a1, const char *Str, unsigned __int16 a3, int *a4)
{
  const char *i; // rbx
  int TypeAndSubType; // edi
  char *v9; // rax
  char *v10; // rdi
  int v11; // ebx
  int v12; // ebx
  char *v13; // rax
  __int64 v14; // rax
  int v15; // ecx
  char *v16; // r10
  __int64 v17; // rcx
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[32]; // [rsp+28h] [rbp-D8h] BYREF
  char *Stra; // [rsp+48h] [rbp-B8h]
  unsigned int v21; // [rsp+50h] [rbp-B0h]
  int v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[32]; // [rsp+60h] [rbp-A0h] BYREF
  char *v24; // [rsp+80h] [rbp-80h]
  _BYTE v25[32]; // [rsp+98h] [rbp-68h] BYREF
  char *String1; // [rsp+B8h] [rbp-48h]
  _BYTE v27[32]; // [rsp+D0h] [rbp-30h] BYREF
  char *v28; // [rsp+F0h] [rbp-10h]
  _BYTE v29[32]; // [rsp+108h] [rbp+8h] BYREF
  char *String2; // [rsp+128h] [rbp+28h]
  char v31[32]; // [rsp+140h] [rbp+40h] BYREF
  char v32[32]; // [rsp+160h] [rbp+60h] BYREF
  char v33[32]; // [rsp+180h] [rbp+80h] BYREF
  char v34[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v35[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  v18[1] = HIDWORD(Str);
  v18[0] = 0;
  i = Str;
  if ( (a3 < 3u || Str[a3 - 1] != 42 || Str[a3 - 2] != 47 || Str[a3 - 3] != 42) && !strstr(Str, "*/*") )
  {
    STRA::STRA((STRA *)v29, v31, 0x20u);
    STRA::STRA((STRA *)v27, v32, 0x20u);
    TypeAndSubType = GetTypeAndSubType(a1, (struct STRA *)v29, (struct STRA *)v27, v18);
    if ( TypeAndSubType >= 0 )
    {
      if ( v18[0] )
      {
        while ( *i == 32 )
          ++i;
        STRA::STRA((STRA *)v19, v35, 0x40u);
        STRA::STRA((STRA *)v25, v33, 0x20u);
        STRA::STRA((STRA *)v23, v34, 0x20u);
        while ( 1 )
        {
          v9 = strchr(i, 44);
          v10 = v9;
          if ( v9 )
          {
            v12 = STRA::Copy((STRA *)v19, i, (_DWORD)v9 - (_DWORD)i);
            if ( v12 < 0 )
            {
              STRA::~STRA((STRA *)v23);
              STRA::~STRA((STRA *)v25);
              STRA::~STRA((STRA *)v19);
              STRA::~STRA((STRA *)v27);
              STRA::~STRA((STRA *)v29);
              return (unsigned int)v12;
            }
          }
          else
          {
            v11 = STRA::Copy((STRA *)v19, i);
            if ( v11 < 0 )
              goto LABEL_17;
          }
          v13 = strchr(Stra, 59);
          if ( v13 )
          {
            v14 = (unsigned int)((_DWORD)v13 - (_DWORD)Stra);
            if ( (unsigned int)v14 < v21 )
            {
              Stra[v14] = 0;
              v22 = v14;
            }
          }
          v15 = v22;
          v16 = Stra;
          do
            --v15;
          while ( v15 >= 0 && Stra[v15] == 32 );
          v17 = (unsigned int)(v15 + 1);
          if ( (unsigned int)v17 < v21 )
          {
            Stra[v17] = 0;
            v16 = Stra;
            v22 = v17;
          }
          v11 = GetTypeAndSubType(v16, (struct STRA *)v25, (struct STRA *)v23, v18);
          if ( v11 < 0 )
          {
LABEL_17:
            STRA::~STRA((STRA *)v23);
            STRA::~STRA((STRA *)v25);
            STRA::~STRA((STRA *)v19);
            TypeAndSubType = v11;
            goto LABEL_18;
          }
          if ( v18[0] && !_stricmp(String1, String2) && (*v24 == 42 && !v24[1] || !_stricmp(v24, v28)) )
          {
            *a4 = 1;
            STRA::~STRA((STRA *)v23);
            STRA::~STRA((STRA *)v25);
            STRA::~STRA((STRA *)v19);
            goto LABEL_11;
          }
          if ( !v10 )
          {
            *a4 = 0;
            STRA::~STRA((STRA *)v23);
            STRA::~STRA((STRA *)v25);
            STRA::~STRA((STRA *)v19);
            STRA::~STRA((STRA *)v27);
            STRA::~STRA((STRA *)v29);
            return 0;
          }
          for ( i = v10 + 1; *i == 32; ++i )
            ;
        }
      }
      *a4 = 0;
LABEL_11:
      TypeAndSubType = 0;
    }
LABEL_18:
    STRA::~STRA((STRA *)v27);
    STRA::~STRA((STRA *)v29);
    return (unsigned int)TypeAndSubType;
  }
  *a4 = 1;
  return 0;
}

```

## disassembly

```asm
0x180017718  push    rbp
0x18001771a  push    rbx
0x18001771b  push    rsi
0x18001771c  push    rdi
0x18001771d  push    r15
0x18001771f  lea     rbp, [rsp-110h]
0x180017727  sub     rsp, 210h
0x18001772e  mov     rax, cs:__security_cookie
0x180017735  xor     rax, rsp
0x180017738  mov     [rbp+130h+var_30], rax
0x18001773f  mov     qword ptr [rsp+230h+var_210], rdx
0x180017744  mov     rsi, r9
0x180017747  mov     [rsp+230h+var_210], 0
0x18001774f  mov     rbx, rdx
0x180017752  mov     rdi, rcx
0x180017755  cmp     r8w, 3
0x18001775a  jb      short loc_180017779
0x18001775c  movzx   eax, r8w
0x180017760  cmp     byte ptr [rax+rdx-1], 2Ah ; '*'
0x180017765  jnz     short loc_180017779
0x180017767  cmp     byte ptr [rax+rdx-2], 2Fh ; '/'
0x18001776c  jnz     short loc_180017779
0x18001776e  movzx   eax, r8w
0x180017772  cmp     byte ptr [rax+rdx-3], 2Ah ; '*'
0x180017777  jz      short loc_18001778E
0x180017779  lea     rdx, SubStr; "*/*"
0x180017780  mov     rcx, rbx; Str
0x180017783  call    cs:__imp_strstr
0x180017789  test    rax, rax
0x18001778c  jz      short loc_18001779B
0x18001778e  mov     dword ptr [rsi], 1
0x180017794  xor     eax, eax
0x180017796  jmp     loc_180017A21
0x18001779b  mov     r15d, 20h ; ' '
0x1800177a1  lea     rdx, [rbp+130h+var_F0]
0x1800177a5  mov     r8d, r15d
0x1800177a8  lea     rcx, [rbp+130h+var_128]
0x1800177ac  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800177b2  mov     r8d, r15d
0x1800177b5  lea     rdx, [rbp+130h+var_D0]
0x1800177b9  lea     rcx, [rbp+130h+var_160]
0x1800177bd  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800177c3  lea     r9, [rsp+230h+var_210]; int *
0x1800177c8  mov     rcx, rdi; char *
0x1800177cb  lea     r8, [rbp+130h+var_160]; struct STRA *
0x1800177cf  lea     rdx, [rbp+130h+var_128]; struct STRA *
0x1800177d3  call    ?GetTypeAndSubType@@YAJPEBDPEAVSTRA@@1PEAH@Z; GetTypeAndSubType(char const *,STRA *,STRA *,int *)
0x1800177d8  mov     edi, eax
0x1800177da  test    eax, eax
0x1800177dc  js      loc_18001788B
0x1800177e2  cmp     [rsp+230h+var_210], 0
0x1800177e7  jnz     short loc_1800177F9
0x1800177e9  mov     dword ptr [rsi], 0
0x1800177ef  xor     edi, edi
0x1800177f1  jmp     loc_18001788B
0x1800177f6  inc     rbx
0x1800177f9  cmp     [rbx], r15b
0x1800177fc  jz      short loc_1800177F6
0x1800177fe  mov     r8d, 40h ; '@'
0x180017804  lea     rdx, [rbp+130h+var_70]
0x18001780b  lea     rcx, [rsp+230h+var_208]
0x180017810  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180017816  mov     r8d, r15d
0x180017819  lea     rdx, [rbp+130h+var_B0]
0x180017820  lea     rcx, [rbp+130h+var_198]
0x180017824  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18001782a  mov     r8d, r15d
0x18001782d  lea     rdx, [rbp+130h+var_90]
0x180017834  lea     rcx, [rsp+230h+var_1D0]
0x180017839  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18001783f  mov     edx, 2Ch ; ','; Val
0x180017844  mov     rcx, rbx; Str
0x180017847  call    cs:__imp_strchr
0x18001784d  mov     rdx, rbx
0x180017850  lea     rcx, [rsp+230h+var_208]
0x180017855  mov     rdi, rax
0x180017858  test    rax, rax
0x18001785b  jnz     short loc_1800178A6
0x18001785d  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180017863  mov     ebx, eax
0x180017865  test    eax, eax
0x180017867  jns     short loc_1800178BC
0x180017869  lea     rcx, [rsp+230h+var_1D0]
0x18001786e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180017874  lea     rcx, [rbp+130h+var_198]
0x180017878  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001787e  lea     rcx, [rsp+230h+var_208]
0x180017883  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180017889  mov     edi, ebx
0x18001788b  lea     rcx, [rbp+130h+var_160]
0x18001788f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180017895  lea     rcx, [rbp+130h+var_128]
0x180017899  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001789f  mov     eax, edi
0x1800178a1  jmp     loc_180017A21
0x1800178a6  mov     r8d, edi
0x1800178a9  sub     r8d, ebx
0x1800178ac  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800178b2  mov     ebx, eax
0x1800178b4  test    eax, eax
0x1800178b6  js      loc_1800179EB
0x1800178bc  mov     rcx, [rsp+230h+Str]; Str
0x1800178c1  mov     edx, 3Bh ; ';'; Val
0x1800178c6  call    cs:__imp_strchr
0x1800178cc  test    rax, rax
0x1800178cf  jz      short loc_1800178E8
0x1800178d1  sub     eax, dword ptr [rsp+230h+Str]
0x1800178d5  cmp     eax, [rsp+230h+var_1E0]
0x1800178d9  jnb     short loc_1800178E8
0x1800178db  mov     rcx, [rsp+230h+Str]
0x1800178e0  mov     byte ptr [rax+rcx], 0
0x1800178e4  mov     [rsp+230h+var_1D8], eax
0x1800178e8  mov     ecx, [rsp+230h+var_1D8]
0x1800178ec  mov     r10, [rsp+230h+Str]
0x1800178f1  jmp     short loc_1800178F9
0x1800178f3  cmp     [rcx+r10], r15b
0x1800178f7  jnz     short loc_1800178FE
0x1800178f9  sub     ecx, 1
0x1800178fc  jns     short loc_1800178F3
0x1800178fe  inc     ecx
0x180017900  cmp     ecx, [rsp+230h+var_1E0]
0x180017904  jnb     short loc_180017914
0x180017906  mov     byte ptr [rcx+r10], 0
0x18001790b  mov     r10, [rsp+230h+Str]
0x180017910  mov     [rsp+230h+var_1D8], ecx
0x180017914  lea     r9, [rsp+230h+var_210]; int *
0x180017919  mov     rcx, r10; char *
0x18001791c  lea     r8, [rsp+230h+var_1D0]; struct STRA *
0x180017921  lea     rdx, [rbp+130h+var_198]; struct STRA *
0x180017925  call    ?GetTypeAndSubType@@YAJPEBDPEAVSTRA@@1PEAH@Z; GetTypeAndSubType(char const *,STRA *,STRA *,int *)
0x18001792a  mov     ebx, eax
0x18001792c  test    eax, eax
0x18001792e  js      loc_180017869
0x180017934  cmp     [rsp+230h+var_210], 0
0x180017939  jz      short loc_180017969
0x18001793b  mov     rdx, [rbp+130h+String2]; String2
0x18001793f  mov     rcx, [rbp+130h+String1]; String1
0x180017943  call    cs:__imp__stricmp
0x180017949  test    eax, eax
0x18001794b  jnz     short loc_180017969
0x18001794d  mov     rcx, [rbp+130h+var_1B0]; String1
0x180017951  cmp     byte ptr [rcx], 2Ah ; '*'
0x180017954  jnz     short loc_18001795B
0x180017956  cmp     [rcx+1], al
0x180017959  jz      short loc_180017981
0x18001795b  mov     rdx, [rbp+130h+var_140]; String2
0x18001795f  call    cs:__imp__stricmp
0x180017965  test    eax, eax
0x180017967  jz      short loc_180017981
0x180017969  test    rdi, rdi
0x18001796c  jz      short loc_1800179AC
0x18001796e  lea     rbx, [rdi+1]
0x180017972  jmp     short loc_180017977
0x180017974  inc     rbx
0x180017977  cmp     [rbx], r15b
0x18001797a  jz      short loc_180017974
0x18001797c  jmp     loc_18001783F
0x180017981  lea     rcx, [rsp+230h+var_1D0]
0x180017986  mov     dword ptr [rsi], 1
0x18001798c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180017992  lea     rcx, [rbp+130h+var_198]
0x180017996  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001799c  lea     rcx, [rsp+230h+var_208]
0x1800179a1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800179a7  jmp     loc_1800177EF
0x1800179ac  lea     rcx, [rsp+230h+var_1D0]
0x1800179b1  mov     dword ptr [rsi], 0
0x1800179b7  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800179bd  lea     rcx, [rbp+130h+var_198]
0x1800179c1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800179c7  lea     rcx, [rsp+230h+var_208]
0x1800179cc  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800179d2  lea     rcx, [rbp+130h+var_160]
0x1800179d6  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800179dc  lea     rcx, [rbp+130h+var_128]
0x1800179e0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800179e6  jmp     loc_180017794
0x1800179eb  lea     rcx, [rsp+230h+var_1D0]
0x1800179f0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800179f6  lea     rcx, [rbp+130h+var_198]
0x1800179fa  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180017a00  lea     rcx, [rsp+230h+var_208]
0x180017a05  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180017a0b  lea     rcx, [rbp+130h+var_160]
0x180017a0f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180017a15  lea     rcx, [rbp+130h+var_128]
0x180017a19  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180017a1f  mov     eax, ebx
0x180017a21  mov     rcx, [rbp+130h+var_30]
0x180017a28  xor     rcx, rsp; StackCookie
0x180017a2b  call    __security_check_cookie
0x180017a30  add     rsp, 210h
0x180017a37  pop     r15
0x180017a39  pop     rdi
0x180017a3a  pop     rsi
0x180017a3b  pop     rbx
0x180017a3c  pop     rbp
0x180017a3d  retn
```
